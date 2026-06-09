# WscDSA_StartDefaultApplyThread(CWmiEventManagerAvFw *,CThirdPartyManager *,ulong)

- ea: `0x18003cfe8`
- end: `0x18003d0fa`
- name: `?WscDSA_StartDefaultApplyThread@@YAJPEAVCWmiEventManagerAvFw@@PEAVCThirdPartyManager@@K@Z`
- size: `274`
- prototype: `__int64 __fastcall(struct CWmiEventManagerAvFw *, struct CThirdPartyManager *, unsigned int)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18003b71c`
- `0x18003b824`
- `0x18003d100`

## callees

- `0x180008e48`
- `0x1800202e8`
- `0x18003cfe8`

## import_xrefs

- `msvcrt!malloc` at `0x18003d038`
- `msvcrt!malloc` at `0x18003d038`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d0a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d0a4`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18003d099`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18003d099`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003d0bb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003d0bb`

## pseudocode

```c
signed int __fastcall WscDSA_StartDefaultApplyThread(
        struct CWmiEventManagerAvFw *a1,
        struct CThirdPartyManager *a2,
        int a3)
{
  CThirdPartyManager *v6; // rbx
  _QWORD *v7; // rdi
  signed int result; // eax
  HANDLE Thread; // rax

  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 89, WPP_728c66c465713f49a85befae87578f6c_Traceguids);
    v6 = WPP_GLOBAL_Control;
  }
  v7 = malloc(0x18u);
  if ( !v7 )
    return -2147024888;
  if ( v6 != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)v6 + 2), 90, WPP_728c66c465713f49a85befae87578f6c_Traceguids);
  v7[1] = a2;
  *v7 = a1;
  *((_DWORD *)v7 + 4) = a3;
  Thread = CreateThread(0, 0, WscDSA_ApplyDefaultThread, v7, 0, 0);
  if ( Thread )
  {
    CloseHandle(Thread);
    if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 91, WPP_728c66c465713f49a85befae87578f6c_Traceguids, 0);
    }
    return 0;
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x18003cfe8  push    rbx
0x18003cfea  push    rbp
0x18003cfeb  push    rsi
0x18003cfec  push    rdi
0x18003cfed  push    r14
0x18003cfef  push    r15
0x18003cff1  sub     rsp, 38h
0x18003cff5  mov     esi, r8d
0x18003cff8  mov     rbp, rdx
0x18003cffb  mov     r14, rcx
0x18003cffe  mov     rbx, cs:WPP_GLOBAL_Control
0x18003d005  lea     r15, WPP_GLOBAL_Control
0x18003d00c  cmp     rbx, r15
0x18003d00f  jz      short loc_18003D033
0x18003d011  test    byte ptr [rbx+1Ch], 8
0x18003d015  jz      short loc_18003D033
0x18003d017  mov     rcx, [rbx+10h]
0x18003d01b  lea     r8, WPP_728c66c465713f49a85befae87578f6c_Traceguids
0x18003d022  mov     edx, 59h ; 'Y'
0x18003d027  call    WPP_SF_
0x18003d02c  mov     rbx, cs:WPP_GLOBAL_Control
0x18003d033  mov     ecx, 18h; Size
0x18003d038  call    cs:__imp_malloc
0x18003d03e  mov     rdi, rax
0x18003d041  test    rax, rax
0x18003d044  jnz     short loc_18003D050
0x18003d046  mov     eax, 80070008h
0x18003d04b  jmp     loc_18003D0ED
0x18003d050  cmp     rbx, r15
0x18003d053  jz      short loc_18003D070
0x18003d055  test    byte ptr [rbx+1Ch], 4
0x18003d059  jz      short loc_18003D070
0x18003d05b  mov     rcx, [rbx+10h]
0x18003d05f  lea     r8, WPP_728c66c465713f49a85befae87578f6c_Traceguids
0x18003d066  mov     edx, 5Ah ; 'Z'
0x18003d06b  call    WPP_SF_
0x18003d070  mov     [rsp+68h+lpThreadId], 0; lpThreadId
0x18003d079  lea     r8, ?WscDSA_ApplyDefaultThread@@YAKPEAU_DefaultProductRemediationArgs@@@Z; lpStartAddress
0x18003d080  mov     r9, rdi; lpParameter
0x18003d083  mov     [rsp+68h+dwCreationFlags], 0; dwCreationFlags
0x18003d08b  xor     edx, edx; dwStackSize
0x18003d08d  mov     [rdi+8], rbp
0x18003d091  xor     ecx, ecx; lpThreadAttributes
0x18003d093  mov     [rdi], r14
0x18003d096  mov     [rdi+10h], esi
0x18003d099  call    cs:__imp_CreateThread
0x18003d09f  test    rax, rax
0x18003d0a2  jnz     short loc_18003D0B8
0x18003d0a4  call    cs:__imp_GetLastError
0x18003d0aa  test    eax, eax
0x18003d0ac  jle     short loc_18003D0ED
0x18003d0ae  movzx   eax, ax
0x18003d0b1  or      eax, 80070000h
0x18003d0b6  jmp     short loc_18003D0ED
0x18003d0b8  mov     rcx, rax; hObject
0x18003d0bb  call    cs:__imp_CloseHandle
0x18003d0c1  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d0c8  cmp     rcx, r15
0x18003d0cb  jz      short loc_18003D0EB
0x18003d0cd  test    byte ptr [rcx+1Ch], 8
0x18003d0d1  jz      short loc_18003D0EB
0x18003d0d3  mov     rcx, [rcx+10h]
0x18003d0d7  lea     r8, WPP_728c66c465713f49a85befae87578f6c_Traceguids
0x18003d0de  mov     edx, 5Bh ; '['
0x18003d0e3  xor     r9d, r9d
0x18003d0e6  call    WPP_SF_d
0x18003d0eb  xor     eax, eax
0x18003d0ed  add     rsp, 38h
0x18003d0f1  pop     r15
0x18003d0f3  pop     r14
0x18003d0f5  pop     rdi
0x18003d0f6  pop     rsi
0x18003d0f7  pop     rbp
0x18003d0f8  pop     rbx
0x18003d0f9  retn
```
