# ATL::IConnectionPointImpl<CTDCCtl,&_GUID const IID_ITDCCtlEvents,ATL::CComDynamicUnkArray>::Unadvise(ulong)

- ea: `0x180009720`
- end: `0x180009795`
- name: `?Unadvise@?$IConnectionPointImpl@VCTDCCtl@@$1?IID_ITDCCtlEvents@@3U_GUID@@BVCComDynamicUnkArray@ATL@@@ATL@@UEAAJK@Z`
- size: `117`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180009720`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall ATL::IConnectionPointImpl<CTDCCtl,&_GUID const IID_ITDCCtlEvents,ATL::CComDynamicUnkArray>::Unadvise(
        __int64 a1,
        unsigned int a2)
{
  __int64 v2; // r8
  signed int v3; // eax
  __int64 v4; // rcx
  unsigned int v5; // eax
  unsigned int v6; // ebx

  v2 = a1 + 8;
  if ( a2 && a2 <= *(_DWORD *)(a1 + 16) && (v3 = a2 - 1, (int)(a2 - 1) >= 0) && v3 < *(_DWORD *)(a1 + 16) )
  {
    _mm_lfence();
    v4 = *(_QWORD *)(*(_QWORD *)v2 + 8LL * v3);
  }
  else
  {
    v4 = 0;
  }
  v5 = a2 - 1;
  if ( a2 && v5 < *(_DWORD *)(v2 + 8) && *(_QWORD *)(*(_QWORD *)v2 + 8LL * v5) )
  {
    v6 = 0;
    *(_QWORD *)(*(_QWORD *)v2 + 8LL * v5) = 0;
    if ( v4 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  }
  else
  {
    return (unsigned int)-2147220992;
  }
  return v6;
}

```

## disassembly

```asm
0x180009720  push    rbx
0x180009722  sub     rsp, 20h
0x180009726  lea     r8, [rcx+8]
0x18000972a  test    edx, edx
0x18000972c  jz      short loc_180009750
0x18000972e  cmp     edx, [r8+8]
0x180009732  ja      short loc_180009750
0x180009734  lea     eax, [rdx-1]
0x180009737  test    eax, eax
0x180009739  js      short loc_180009750
0x18000973b  cmp     eax, [r8+8]
0x18000973f  jge     short loc_180009750
0x180009741  lfence
0x180009744  movsxd  rcx, eax
0x180009747  mov     rax, [r8]
0x18000974a  mov     rcx, [rax+rcx*8]
0x18000974e  jmp     short loc_180009752
0x180009750  xor     ecx, ecx
0x180009752  lea     eax, [rdx-1]
0x180009755  cmp     eax, edx
0x180009757  jnb     short loc_180009788
0x180009759  cmp     eax, [r8+8]
0x18000975d  jnb     short loc_180009788
0x18000975f  mov     edx, eax
0x180009761  mov     rax, [r8]
0x180009764  cmp     qword ptr [rax+rdx*8], 0
0x180009769  jz      short loc_180009788
0x18000976b  xor     ebx, ebx
0x18000976d  mov     qword ptr [rax+rdx*8], 0
0x180009775  test    rcx, rcx
0x180009778  jz      short loc_18000978D
0x18000977a  mov     rax, [rcx]
0x18000977d  mov     rax, [rax+10h]
0x180009781  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009786  jmp     short loc_18000978D
0x180009788  mov     ebx, 80040200h
0x18000978d  mov     eax, ebx
0x18000978f  add     rsp, 20h
0x180009793  pop     rbx
0x180009794  retn
```
