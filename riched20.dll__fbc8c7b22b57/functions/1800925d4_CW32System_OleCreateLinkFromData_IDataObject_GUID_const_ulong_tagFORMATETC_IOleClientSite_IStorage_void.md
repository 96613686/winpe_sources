# CW32System::OleCreateLinkFromData(IDataObject *,_GUID const &,ulong,tagFORMATETC *,IOleClientSite *,IStorage *,void * *)

- ea: `0x1800925d4`
- end: `0x180092667`
- name: `?OleCreateLinkFromData@CW32System@@SAJPEAUIDataObject@@AEBU_GUID@@KPEAUtagFORMATETC@@PEAUIOleClientSite@@PEAUIStorage@@PEAPEAX@Z`
- size: `147`
- prototype: `__int64 __fastcall(struct IDataObject *, const struct _GUID *, unsigned int, struct tagFORMATETC *, struct IOleClientSite *, struct IStorage *, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18006e1f8`

## callees

- `0x1800427ac`
- `0x1800925d4`
- `0x1800931b0`
- `0x180095010`

## string_xrefs

- `0x1800925fb`: `OleCreateLinkFromData`

## pseudocode

```c
__int64 __fastcall CW32System::OleCreateLinkFromData(
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
  v10 = (__int64 (__fastcall **)(struct IDataObject *, GUID *, __int64, struct tagFORMATETC *, _QWORD, struct IStorage *, void **))((char *)Ole32Procs + 176);
  if ( !*((_QWORD *)Ole32Procs + 22) )
    SetProcAddr((FARPROC *)Ole32Procs + 22, 1, "OleCreateLinkFromData");
  if ( *v10 )
    return (*v10)(a1, &IID_IOleObject, 1, a4, 0, a6, a7);
  else
    return 2147500037LL;
}

```

## disassembly

```asm
0x1800925d4  mov     [rsp+arg_0], rbx
0x1800925d9  mov     [rsp+arg_8], rsi
0x1800925de  push    rdi
0x1800925df  sub     rsp, 40h
0x1800925e3  mov     rdi, r9
0x1800925e6  mov     rsi, rcx
0x1800925e9  call    ?GetOle32Procs@CThreadData@@SAPEAVCOLE32_PROC@@XZ; CThreadData::GetOle32Procs(void)
0x1800925ee  lea     rbx, [rax+0B0h]
0x1800925f5  cmp     qword ptr [rbx], 0
0x1800925f9  jnz     short loc_18009260F
0x1800925fb  lea     r8, aOlecreatelinkf; "OleCreateLinkFromData"
0x180092602  mov     edx, 1
0x180092607  mov     rcx, rbx
0x18009260a  call    SetProcAddr
0x18009260f  mov     rax, [rbx]
0x180092612  test    rax, rax
0x180092615  jz      short loc_180092651
0x180092617  mov     rcx, [rsp+48h+arg_30]
0x18009261f  lea     rdx, IID_IOleObject
0x180092626  mov     [rsp+48h+var_18], rcx
0x18009262b  mov     r9, rdi
0x18009262e  mov     rcx, [rsp+48h+arg_28]
0x180092633  mov     r8d, 1
0x180092639  mov     [rsp+48h+var_20], rcx
0x18009263e  mov     rcx, rsi
0x180092641  mov     [rsp+48h+var_28], 0
0x18009264a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009264f  jmp     short loc_180092656
0x180092651  mov     eax, 80004005h
0x180092656  mov     rbx, [rsp+48h+arg_0]
0x18009265b  mov     rsi, [rsp+48h+arg_8]
0x180092660  add     rsp, 40h
0x180092664  pop     rdi
0x180092665  retn
```
