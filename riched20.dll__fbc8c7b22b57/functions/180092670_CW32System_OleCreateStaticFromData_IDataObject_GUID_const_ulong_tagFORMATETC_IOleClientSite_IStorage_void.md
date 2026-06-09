# CW32System::OleCreateStaticFromData(IDataObject *,_GUID const &,ulong,tagFORMATETC *,IOleClientSite *,IStorage *,void * *)

- ea: `0x180092670`
- end: `0x180092703`
- name: `?OleCreateStaticFromData@CW32System@@SAJPEAUIDataObject@@AEBU_GUID@@KPEAUtagFORMATETC@@PEAUIOleClientSite@@PEAUIStorage@@PEAPEAX@Z`
- size: `147`
- prototype: `__int64 __fastcall(struct IDataObject *, const struct _GUID *, unsigned int, struct tagFORMATETC *, struct IOleClientSite *, struct IStorage *, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18006e1f8`

## callees

- `0x1800427ac`
- `0x180092670`
- `0x1800931b0`
- `0x180095010`

## string_xrefs

- `0x180092697`: `OleCreateStaticFromData`

## pseudocode

```c
__int64 __fastcall CW32System::OleCreateStaticFromData(
        struct IDataObject *a1,
        const struct _GUID *a2,
        __int64 a3,
        struct tagFORMATETC *a4,
        struct IOleClientSite *a5,
        struct IStorage *a6,
        void **a7)
{
  struct COLE32_PROC *Ole32Procs; // rax
  __int64 (__fastcall **v10)(struct IDataObject *, GUID *, __int64, struct tagFORMATETC *, _QWORD, struct IStorage *, void **); // rbx

  Ole32Procs = CThreadData::GetOle32Procs();
  v10 = (__int64 (__fastcall **)(struct IDataObject *, GUID *, __int64, struct tagFORMATETC *, _QWORD, struct IStorage *, void **))((char *)Ole32Procs + 184);
  if ( !*((_QWORD *)Ole32Procs + 23) )
    SetProcAddr((FARPROC *)Ole32Procs + 23, 1, "OleCreateStaticFromData");
  if ( *v10 )
    return (*v10)(a1, &IID_IOleObject, 1, a4, 0, a6, a7);
  else
    return 2147500037LL;
}

```

## disassembly

```asm
0x180092670  mov     [rsp+arg_0], rbx
0x180092675  mov     [rsp+arg_8], rsi
0x18009267a  push    rdi
0x18009267b  sub     rsp, 40h
0x18009267f  mov     rdi, r9
0x180092682  mov     rsi, rcx
0x180092685  call    ?GetOle32Procs@CThreadData@@SAPEAVCOLE32_PROC@@XZ; CThreadData::GetOle32Procs(void)
0x18009268a  lea     rbx, [rax+0B8h]
0x180092691  cmp     qword ptr [rbx], 0
0x180092695  jnz     short loc_1800926AB
0x180092697  lea     r8, aOlecreatestati; "OleCreateStaticFromData"
0x18009269e  mov     edx, 1
0x1800926a3  mov     rcx, rbx
0x1800926a6  call    SetProcAddr
0x1800926ab  mov     rax, [rbx]
0x1800926ae  test    rax, rax
0x1800926b1  jz      short loc_1800926ED
0x1800926b3  mov     rcx, [rsp+48h+arg_30]
0x1800926bb  lea     rdx, IID_IOleObject
0x1800926c2  mov     [rsp+48h+var_18], rcx
0x1800926c7  mov     r9, rdi
0x1800926ca  mov     rcx, [rsp+48h+arg_28]
0x1800926cf  mov     r8d, 1
0x1800926d5  mov     [rsp+48h+var_20], rcx
0x1800926da  mov     rcx, rsi
0x1800926dd  mov     [rsp+48h+var_28], 0
0x1800926e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800926eb  jmp     short loc_1800926F2
0x1800926ed  mov     eax, 80004005h
0x1800926f2  mov     rbx, [rsp+48h+arg_0]
0x1800926f7  mov     rsi, [rsp+48h+arg_8]
0x1800926fc  add     rsp, 40h
0x180092700  pop     rdi
0x180092701  retn
```
