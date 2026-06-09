# CW32System::OleCreateFromData(IDataObject *,_GUID const &,ulong,tagFORMATETC *,IOleClientSite *,IStorage *,void * *)

- ea: `0x18009253c`
- end: `0x1800925cb`
- name: `?OleCreateFromData@CW32System@@SAJPEAUIDataObject@@AEBU_GUID@@KPEAUtagFORMATETC@@PEAUIOleClientSite@@PEAUIStorage@@PEAPEAX@Z`
- size: `143`
- prototype: `__int64 __fastcall(struct IDataObject *, const struct _GUID *, unsigned int, struct tagFORMATETC *, struct IOleClientSite *, struct IStorage *, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18006e1f8`

## callees

- `0x1800427ac`
- `0x18009253c`
- `0x1800931b0`
- `0x180095010`

## string_xrefs

- `0x18009255f`: `OleCreateFromData`

## pseudocode

```c
__int64 __fastcall CW32System::OleCreateFromData(
        struct IDataObject *a1,
        const struct _GUID *a2,
        __int64 a3,
        struct tagFORMATETC *a4,
        struct IOleClientSite *a5,
        struct IStorage *a6,
        void **a7)
{
  FARPROC *Ole32Procs; // rax
  __int64 (__fastcall **v10)(struct IDataObject *, GUID *, __int64, struct tagFORMATETC *, _QWORD, struct IStorage *, void **); // rbx

  Ole32Procs = (FARPROC *)CThreadData::GetOle32Procs();
  v10 = (__int64 (__fastcall **)(struct IDataObject *, GUID *, __int64, struct tagFORMATETC *, _QWORD, struct IStorage *, void **))Ole32Procs;
  if ( !*Ole32Procs )
    SetProcAddr(Ole32Procs, 1, "OleCreateFromData");
  if ( *v10 )
    return (*v10)(a1, &IID_IOleObject, 1, a4, 0, a6, a7);
  else
    return 2147500037LL;
}

```

## disassembly

```asm
0x18009253c  mov     [rsp+arg_0], rbx
0x180092541  mov     [rsp+arg_8], rsi
0x180092546  push    rdi
0x180092547  sub     rsp, 40h
0x18009254b  mov     rdi, r9
0x18009254e  mov     rsi, rcx
0x180092551  call    ?GetOle32Procs@CThreadData@@SAPEAVCOLE32_PROC@@XZ; CThreadData::GetOle32Procs(void)
0x180092556  mov     rbx, rax
0x180092559  cmp     qword ptr [rax], 0
0x18009255d  jnz     short loc_180092573
0x18009255f  lea     r8, aOlecreatefromd; "OleCreateFromData"
0x180092566  mov     edx, 1
0x18009256b  mov     rcx, rax
0x18009256e  call    SetProcAddr
0x180092573  mov     rax, [rbx]
0x180092576  test    rax, rax
0x180092579  jz      short loc_1800925B5
0x18009257b  mov     rcx, [rsp+48h+arg_30]
0x180092583  lea     rdx, IID_IOleObject
0x18009258a  mov     [rsp+48h+var_18], rcx
0x18009258f  mov     r9, rdi
0x180092592  mov     rcx, [rsp+48h+arg_28]
0x180092597  mov     r8d, 1
0x18009259d  mov     [rsp+48h+var_20], rcx
0x1800925a2  mov     rcx, rsi
0x1800925a5  mov     [rsp+48h+var_28], 0
0x1800925ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800925b3  jmp     short loc_1800925BA
0x1800925b5  mov     eax, 80004005h
0x1800925ba  mov     rbx, [rsp+48h+arg_0]
0x1800925bf  mov     rsi, [rsp+48h+arg_8]
0x1800925c4  add     rsp, 40h
0x1800925c8  pop     rdi
0x1800925c9  retn
```
