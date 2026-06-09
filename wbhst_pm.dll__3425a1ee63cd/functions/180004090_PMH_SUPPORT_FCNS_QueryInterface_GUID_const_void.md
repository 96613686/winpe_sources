# PMH_SUPPORT_FCNS::QueryInterface(_GUID const &,void * *)

- ea: `0x180004090`
- end: `0x1800041b7`
- name: `?QueryInterface@PMH_SUPPORT_FCNS@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `295`
- prototype: `__int64 __fastcall(LPUNKNOWN punkOuter, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800025c0`

## callees

- `0x180004090`
- `0x180005010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004148`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004148`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004185`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004185`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x180004160`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x180004160`

## pseudocode

```c
__int64 __fastcall PMH_SUPPORT_FCNS::QueryInterface(LPUNKNOWN punkOuter, const struct _GUID *a2, void **a3)
{
  LPUNKNOWN v5; // rbx
  HRESULT FreeThreadedMarshaler; // esi
  struct IUnknownVtbl *lpVtbl; // rax
  struct _RTL_CRITICAL_SECTION *v8; // rbp

  v5 = punkOuter;
  if ( !a3 )
    return (unsigned int)-2147024809;
  FreeThreadedMarshaler = 0;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IUnknown.Data1 && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IUnknown.Data4
    || *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_35f9c4c1_3800_4d17_99bc_018a62243687.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)GUID_35f9c4c1_3800_4d17_99bc_018a62243687.Data4 )
  {
    *a3 = punkOuter;
    lpVtbl = punkOuter->lpVtbl;
LABEL_18:
    ((void (__fastcall *)(LPUNKNOWN))lpVtbl->AddRef)(punkOuter);
    return (unsigned int)FreeThreadedMarshaler;
  }
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_940d8add_9e40_4475_9a67_2cdcdf57995c.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)GUID_940d8add_9e40_4475_9a67_2cdcdf57995c.Data4 )
  {
    *a3 = (void *)((unsigned __int64)&punkOuter[1] & -(__int64)(punkOuter != 0));
LABEL_17:
    lpVtbl = v5->lpVtbl;
    punkOuter = v5;
    goto LABEL_18;
  }
  if ( *(_QWORD *)&a2->Data1 != *(_QWORD *)&IID_IMarshal.Data1 || *(_QWORD *)a2->Data4 != *(_QWORD *)IID_IMarshal.Data4 )
  {
    *a3 = 0;
    return (unsigned int)-2147467262;
  }
  v8 = (struct _RTL_CRITICAL_SECTION *)&punkOuter[24];
  *a3 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)&punkOuter[24]);
  if ( v5[29].lpVtbl
    || (FreeThreadedMarshaler = CoCreateFreeThreadedMarshaler(v5, (LPUNKNOWN *)&v5[29]), FreeThreadedMarshaler >= 0) )
  {
    FreeThreadedMarshaler = (*(__int64 (__fastcall **)(struct IUnknownVtbl *, const struct _GUID *, void **))v5[29].lpVtbl->QueryInterface)(
                              v5[29].lpVtbl,
                              a2,
                              a3);
  }
  LeaveCriticalSection(v8);
  if ( FreeThreadedMarshaler >= 0 )
    goto LABEL_17;
  return (unsigned int)FreeThreadedMarshaler;
}

```

## disassembly

```asm
0x180004090  push    rbx
0x180004092  push    rbp
0x180004093  push    rsi
0x180004094  push    rdi
0x180004095  push    r14
0x180004097  push    r15
0x180004099  sub     rsp, 28h
0x18000409d  mov     r14, r8
0x1800040a0  mov     rdi, rdx
0x1800040a3  mov     rbx, rcx
0x1800040a6  test    r8, r8
0x1800040a9  jnz     short loc_1800040B5
0x1800040ab  mov     esi, 80070057h
0x1800040b0  jmp     loc_1800041A8
0x1800040b5  mov     rax, [rdx]
0x1800040b8  xor     esi, esi
0x1800040ba  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x1800040c1  jnz     short loc_1800040D0
0x1800040c3  mov     rax, [rdx+8]
0x1800040c7  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x1800040ce  jz      short loc_1800040E9
0x1800040d0  mov     rax, [rdx]
0x1800040d3  cmp     rax, qword ptr cs:_GUID_35f9c4c1_3800_4d17_99bc_018a62243687.Data1
0x1800040da  jnz     short loc_1800040F4
0x1800040dc  mov     rax, [rdx+8]
0x1800040e0  cmp     rax, qword ptr cs:_GUID_35f9c4c1_3800_4d17_99bc_018a62243687.Data4
0x1800040e7  jnz     short loc_1800040F4
0x1800040e9  mov     [r8], rbx
0x1800040ec  mov     rax, [rcx]
0x1800040ef  jmp     loc_180004195
0x1800040f4  mov     rax, [rdx]
0x1800040f7  cmp     rax, qword ptr cs:_GUID_940d8add_9e40_4475_9a67_2cdcdf57995c.Data1
0x1800040fe  jnz     short loc_180004122
0x180004100  mov     rax, [rdx+8]
0x180004104  cmp     rax, qword ptr cs:_GUID_940d8add_9e40_4475_9a67_2cdcdf57995c.Data4
0x18000410b  jnz     short loc_180004122
0x18000410d  lea     rdx, [rcx+8]
0x180004111  mov     rax, rbx
0x180004114  neg     rax
0x180004117  sbb     rcx, rcx
0x18000411a  and     rcx, rdx
0x18000411d  mov     [r8], rcx
0x180004120  jmp     short loc_18000418F
0x180004122  mov     rax, [rdx]
0x180004125  cmp     rax, qword ptr cs:IID_IMarshal.Data1
0x18000412c  jnz     short loc_1800041A0
0x18000412e  mov     rax, [rdx+8]
0x180004132  cmp     rax, qword ptr cs:IID_IMarshal.Data4
0x180004139  jnz     short loc_1800041A0
0x18000413b  lea     rbp, [rcx+0C0h]
0x180004142  mov     [r8], rsi
0x180004145  mov     rcx, rbp; lpCriticalSection
0x180004148  call    cs:__imp_EnterCriticalSection
0x18000414e  lea     r15, [rbx+0E8h]
0x180004155  cmp     [r15], rsi
0x180004158  jnz     short loc_18000416C
0x18000415a  mov     rdx, r15; ppunkMarshal
0x18000415d  mov     rcx, rbx; punkOuter
0x180004160  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x180004166  mov     esi, eax
0x180004168  test    eax, eax
0x18000416a  js      short loc_180004182
0x18000416c  mov     rcx, [r15]
0x18000416f  mov     r8, r14
0x180004172  mov     rdx, rdi
0x180004175  mov     rax, [rcx]
0x180004178  mov     rax, [rax]
0x18000417b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004180  mov     esi, eax
0x180004182  mov     rcx, rbp; lpCriticalSection
0x180004185  call    cs:__imp_LeaveCriticalSection
0x18000418b  test    esi, esi
0x18000418d  js      short loc_1800041A8
0x18000418f  mov     rax, [rbx]
0x180004192  mov     rcx, rbx
0x180004195  mov     rax, [rax+8]
0x180004199  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000419e  jmp     short loc_1800041A8
0x1800041a0  mov     [r8], rsi
0x1800041a3  mov     esi, 80004002h
0x1800041a8  mov     eax, esi
0x1800041aa  add     rsp, 28h
0x1800041ae  pop     r15
0x1800041b0  pop     r14
0x1800041b2  pop     rdi
0x1800041b3  pop     rsi
0x1800041b4  pop     rbp
0x1800041b5  pop     rbx
0x1800041b6  retn
```
