# CContainer::CreateInstance(_GUID const &,_GUID const &,void * *)

- ea: `0x1400062c0`
- end: `0x14000632b`
- name: `?CreateInstance@CContainer@@UEAAJAEBU_GUID@@0PEAPEAX@Z`
- size: `107`
- prototype: `__int64 __fastcall(CContainer *this, const struct _GUID *, const struct _GUID *, void **ppv)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140005c40`
- `0x1400062c0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1400062e6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1400062e6`

## pseudocode

```c
__int64 __fastcall CContainer::CreateInstance(
        CContainer *this,
        const struct _GUID *a2,
        const struct _GUID *a3,
        void **ppv)
{
  unsigned int Instance; // ebx

  if ( !ppv )
    return 2147500035LL;
  Instance = CoCreateInstance(a2, 0, 1u, a3, ppv);
  if ( Instance
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_5d760b8fc4213c791c7b68ae082a6cff_Traceguids, Instance);
  }
  return Instance;
}

```

## disassembly

```asm
0x1400062c0  push    rbx
0x1400062c2  sub     rsp, 30h
0x1400062c6  mov     rax, rdx
0x1400062c9  test    r9, r9
0x1400062cc  jnz     short loc_1400062D5
0x1400062ce  mov     eax, 80004003h
0x1400062d3  jmp     short loc_140006325
0x1400062d5  xor     edx, edx; pUnkOuter
0x1400062d7  mov     [rsp+38h+ppv], r9; ppv
0x1400062dc  mov     r9, r8; riid
0x1400062df  mov     rcx, rax; rclsid
0x1400062e2  lea     r8d, [rdx+1]; dwClsContext
0x1400062e6  call    cs:__imp_CoCreateInstance
0x1400062ec  mov     ebx, eax
0x1400062ee  test    eax, eax
0x1400062f0  jz      short loc_140006323
0x1400062f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400062f9  lea     rax, WPP_GLOBAL_Control
0x140006300  cmp     rcx, rax
0x140006303  jz      short loc_140006323
0x140006305  test    byte ptr [rcx+1Ch], 1
0x140006309  jz      short loc_140006323
0x14000630b  mov     rcx, [rcx+10h]
0x14000630f  lea     r8, WPP_5d760b8fc4213c791c7b68ae082a6cff_Traceguids
0x140006316  mov     edx, 0Ah
0x14000631b  mov     r9d, ebx
0x14000631e  call    WPP_SF_d
0x140006323  mov     eax, ebx
0x140006325  add     rsp, 30h
0x140006329  pop     rbx
0x14000632a  retn
```
