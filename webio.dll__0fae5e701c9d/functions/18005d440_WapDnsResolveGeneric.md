# WapDnsResolveGeneric

- ea: `0x18005d440`
- end: `0x18005d735`
- name: `WapDnsResolveGeneric`
- size: `757`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18005d3d8`

## callees

- `0x180054794`
- `0x18005d440`
- `0x18005d73c`
- `0x18005d814`
- `0x180065f20`
- `0x1800722f0`
- `0x180072c70`
- `0x180095608`
- `0x1800956a0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18005d5a9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18005d5a9`
- `WS2_32!GetAddrInfoExW` at `0x18005d57a`
- `WS2_32!GetAddrInfoExW` at `0x18005d57a`

## pseudocode

```c
void __fastcall WapDnsResolveGeneric(__int64 a1)
{
  int ai_flags; // ecx
  int v3; // edx
  const WCHAR *v4; // rbx
  unsigned int AddrInfo; // eax
  __int64 v6; // rcx
  int v7; // ebx
  unsigned int IsNameResolutionHandleRequired; // eax
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // r8
  int v12; // ebx
  unsigned int v13; // eax
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // r8
  __int64 v17; // [rsp+50h] [rbp-49h] BYREF
  ADDRINFOEXW hints; // [rsp+60h] [rbp-39h] BYREF
  int v19; // [rsp+A8h] [rbp+Fh]
  int v20; // [rsp+B8h] [rbp+1Fh]

  v17 = a1;
  memset_0(&hints.ai_addrlen, 0, 0x58u);
  *(__m128i *)&hints.ai_flags = _mm_load_si128((const __m128i *)&_xmm);
  if ( *(_DWORD *)(*(_QWORD *)(a1 + 8) + 104LL) )
  {
    v19 = 4;
    v20 = *(_DWORD *)(*(_QWORD *)(a1 + 8) + 104LL);
    hints.ai_flags = -2147352574;
  }
  if ( WaKirDnsResolution )
    hints.ai_family = *(_DWORD *)(*(_QWORD *)(a1 + 8) + 116LL);
  if ( (unsigned int)WaIsNameResolutionHandleRequired() || *(_BYTE *)(*(_QWORD *)(a1 + 8) + 113LL) )
  {
    ai_flags = hints.ai_flags | 0xC0000000;
    v19 = 4;
    hints.ai_flags |= 0xC0000000;
  }
  else
  {
    ai_flags = hints.ai_flags;
  }
  if ( *(_BYTE *)(*(_QWORD *)(a1 + 8) + 115LL) )
  {
    ai_flags |= 0x10u;
    hints.ai_flags = ai_flags;
  }
  if ( *(_BYTE *)(*(_QWORD *)(a1 + 16) + 3173LL) )
  {
    ai_flags |= 0x40u;
    hints.ai_flags = ai_flags;
  }
  v3 = *(_DWORD *)(*(_QWORD *)(a1 + 16) + 3176LL);
  switch ( v3 )
  {
    case 1:
      ai_flags |= 0x20u;
LABEL_14:
      hints.ai_flags = ai_flags;
      break;
    case 2:
      ai_flags |= 0x20000000u;
      goto LABEL_14;
    case 3:
      ai_flags |= 0x100000u;
      goto LABEL_14;
  }
  if ( *(_BYTE *)(*(_QWORD *)(a1 + 16) + 3180LL) )
  {
    ai_flags |= 0x80000080;
    v19 = 5;
    hints.ai_flags = ai_flags;
  }
  if ( WaKirDnsResolution )
  {
    if ( (xmmword_1800AD720 & 8) == 0 )
      goto LABEL_19;
    v7 = *(unsigned __int8 *)(*(_QWORD *)(a1 + 8) + 113LL);
    IsNameResolutionHandleRequired = WaIsNameResolutionHandleRequired();
    WPP_SF_llDDDD(v10, v9, v11, IsNameResolutionHandleRequired, v7, hints.ai_flags, v19, v20, hints.ai_family);
  }
  else
  {
    if ( (xmmword_1800AD720 & 8) == 0 )
      goto LABEL_19;
    v12 = *(unsigned __int8 *)(*(_QWORD *)(a1 + 8) + 113LL);
    v13 = WaIsNameResolutionHandleRequired();
    WPP_SF_llDDD(v15, v14, v16, v13, v12, hints.ai_flags, v19, v20);
  }
  LOBYTE(ai_flags) = hints.ai_flags;
LABEL_19:
  v4 = *(const WCHAR **)(*(_QWORD *)(a1 + 8) + 40LL);
  if ( (Microsoft_Windows_WebIOEnableBits & 0x40) != 0 )
    McTemplateU0pzqqq_EventWriteTransfer(
      (unsigned int)&WEB_ETW_PROVIDER_ID_Context,
      (unsigned int)NetGetAddrInfo,
      a1,
      (_DWORD)v4,
      ai_flags,
      0,
      0);
  AddrInfo = GetAddrInfoExW(v4, 0, 0xCu, 0, &hints, (PADDRINFOEXW *)(a1 + 88), 0, (LPOVERLAPPED)(a1 + 48), 0, 0);
  if ( AddrInfo == 997 )
  {
    if ( (Microsoft_Windows_WebIOEnableBits & 0x20000) != 0 )
      McTemplateU0pq_EventWriteTransfer(v6, ThreadActionQueue, a1 + 48, 3);
    SetThreadpoolWait(*(PTP_WAIT *)(a1 + 96), *(HANDLE *)(a1 + 80), 0);
  }
  else
  {
    WapCompleteDnsGenericIoContext(&v17, AddrInfo);
  }
}

```

## disassembly

```asm
0x18005d440  mov     [rsp-8+arg_8], rbx
0x18005d445  mov     [rsp-8+arg_10], rsi
0x18005d44a  push    rbp
0x18005d44b  push    rdi
0x18005d44c  push    r14
0x18005d44e  lea     rbp, [rsp-47h]
0x18005d453  sub     rsp, 0E0h
0x18005d45a  mov     rax, cs:__security_cookie
0x18005d461  xor     rax, rsp
0x18005d464  mov     [rbp+57h+var_20], rax
0x18005d468  xor     edx, edx; Val
0x18005d46a  mov     [rbp+57h+var_A0], rcx
0x18005d46e  mov     rdi, rcx
0x18005d471  lea     rcx, [rbp+57h+var_90.ai_addrlen]; void *
0x18005d475  lea     r8d, [rdx+58h]; Size
0x18005d479  call    memset_0
0x18005d47e  movdqa  xmm0, cs:__xmm@00000006000000010000000000020002
0x18005d486  lea     rsi, [rdi+30h]
0x18005d48a  movdqa  xmmword ptr [rbp+57h+var_90.ai_flags], xmm0
0x18005d48f  xor     r14d, r14d
0x18005d492  mov     rax, [rdi+8]
0x18005d496  mov     ebx, 4
0x18005d49b  cmp     [rax+68h], r14d
0x18005d49f  jnz     loc_18005D621
0x18005d4a5  cmp     cs:WaKirDnsResolution, r14b
0x18005d4ac  jnz     loc_18005D63A
0x18005d4b2  call    WaIsNameResolutionHandleRequired
0x18005d4b7  test    eax, eax
0x18005d4b9  jnz     loc_18005D649
0x18005d4bf  mov     rax, [rdi+8]
0x18005d4c3  cmp     [rax+71h], r14b
0x18005d4c7  jnz     loc_18005D649
0x18005d4cd  mov     ecx, [rbp+57h+var_90.ai_flags]
0x18005d4d0  mov     rax, [rdi+8]
0x18005d4d4  cmp     [rax+73h], r14b
0x18005d4d8  jnz     loc_18005D65D
0x18005d4de  mov     rax, [rdi+10h]
0x18005d4e2  cmp     [rax+0C65h], r14b
0x18005d4e9  jnz     loc_18005D668
0x18005d4ef  mov     rax, [rdi+10h]
0x18005d4f3  mov     edx, [rax+0C68h]
0x18005d4f9  cmp     edx, 1
0x18005d4fc  jnz     loc_18005D5DA
0x18005d502  or      ecx, 20h
0x18005d505  mov     [rbp+57h+var_90.ai_flags], ecx
0x18005d508  mov     rax, [rdi+10h]
0x18005d50c  cmp     [rax+0C6Ch], r14b
0x18005d513  jnz     loc_18005D67C
0x18005d519  cmp     cs:WaKirDnsResolution, r14b
0x18005d520  jnz     loc_18005D691
0x18005d526  test    byte ptr cs:xmmword_1800AD720, 8
0x18005d52d  jnz     loc_18005D6D5
0x18005d533  test    byte ptr cs:Microsoft_Windows_WebIOEnableBits, 40h
0x18005d53a  mov     rax, [rdi+8]
0x18005d53e  mov     rbx, [rax+28h]
0x18005d542  jnz     loc_18005D5F5
0x18005d548  mov     [rsp+0F0h+lpHandle], r14; lpHandle
0x18005d54d  lea     rax, [rdi+58h]
0x18005d551  mov     [rsp+0F0h+lpCompletionRoutine], r14; lpCompletionRoutine
0x18005d556  xor     r9d, r9d; lpNspId
0x18005d559  mov     [rsp+0F0h+lpOverlapped], rsi; lpOverlapped
0x18005d55e  xor     edx, edx; pServiceName
0x18005d560  mov     [rsp+0F0h+timeout], r14; timeout
0x18005d565  mov     rcx, rbx; pName
0x18005d568  mov     [rsp+0F0h+ppResult], rax; ppResult
0x18005d56d  lea     rax, [rbp+57h+var_90]
0x18005d571  lea     r8d, [r9+0Ch]; dwNameSpace
0x18005d575  mov     [rsp+0F0h+hints], rax; hints
0x18005d57a  call    cs:__imp_GetAddrInfoExW
0x18005d581  nop     dword ptr [rax+rax+00h]
0x18005d586  cmp     eax, 3E5h
0x18005d58b  jnz     loc_18005D70B
0x18005d591  test    byte ptr cs:Microsoft_Windows_WebIOEnableBits+2, 2
0x18005d598  jnz     loc_18005D71B
0x18005d59e  mov     rdx, [rdi+50h]; h
0x18005d5a2  xor     r8d, r8d; pftTimeout
0x18005d5a5  mov     rcx, [rdi+60h]; pwa
0x18005d5a9  call    cs:__imp_SetThreadpoolWait
0x18005d5b0  nop     dword ptr [rax+rax+00h]
0x18005d5b5  mov     rcx, [rbp+57h+var_20]
0x18005d5b9  xor     rcx, rsp; StackCookie
0x18005d5bc  call    __security_check_cookie
0x18005d5c1  lea     r11, [rsp+0F0h+var_10]
0x18005d5c9  mov     rbx, [r11+28h]
0x18005d5cd  mov     rsi, [r11+30h]
0x18005d5d1  mov     rsp, r11
0x18005d5d4  pop     r14
0x18005d5d6  pop     rdi
0x18005d5d7  pop     rbp
0x18005d5d8  retn
0x18005d5da  cmp     edx, 2
0x18005d5dd  jz      loc_18005D673
0x18005d5e3  cmp     edx, 3
0x18005d5e6  jnz     loc_18005D508
0x18005d5ec  bts     ecx, 14h
0x18005d5f0  jmp     loc_18005D505
0x18005d5f5  mov     dword ptr [rsp+0F0h+timeout], r14d
0x18005d5fa  lea     rdx, NetGetAddrInfo
0x18005d601  mov     dword ptr [rsp+0F0h+ppResult], r14d
0x18005d606  mov     r9, rbx
0x18005d609  mov     dword ptr [rsp+0F0h+hints], ecx
0x18005d60d  mov     r8, rdi
0x18005d610  lea     rcx, WEB_ETW_PROVIDER_ID_Context
0x18005d617  call    McTemplateU0pzqqq_EventWriteTransfer
0x18005d61c  jmp     loc_18005D548
0x18005d621  mov     [rbp+57h+var_48], ebx
0x18005d624  mov     rax, [rdi+8]
0x18005d628  mov     ecx, [rax+68h]
0x18005d62b  mov     [rbp+57h+var_38], ecx
0x18005d62e  mov     [rbp+57h+var_90.ai_flags], 80020002h
0x18005d635  jmp     loc_18005D4A5
0x18005d63a  mov     rax, [rdi+8]
0x18005d63e  mov     ecx, [rax+74h]
0x18005d641  mov     [rbp+57h+var_90.ai_family], ecx
0x18005d644  jmp     loc_18005D4B2
0x18005d649  mov     ecx, [rbp+57h+var_90.ai_flags]
0x18005d64c  or      ecx, 0C0000000h
0x18005d652  mov     [rbp+57h+var_48], ebx
0x18005d655  mov     [rbp+57h+var_90.ai_flags], ecx
0x18005d658  jmp     loc_18005D4D0
0x18005d65d  or      ecx, 10h
0x18005d660  mov     [rbp+57h+var_90.ai_flags], ecx
0x18005d663  jmp     loc_18005D4DE
0x18005d668  or      ecx, 40h
0x18005d66b  mov     [rbp+57h+var_90.ai_flags], ecx
0x18005d66e  jmp     loc_18005D4EF
0x18005d673  bts     ecx, 1Dh
0x18005d677  jmp     loc_18005D505
0x18005d67c  or      ecx, 80000080h
0x18005d682  mov     [rbp+57h+var_48], 5
0x18005d689  mov     [rbp+57h+var_90.ai_flags], ecx
0x18005d68c  jmp     loc_18005D519
0x18005d691  test    byte ptr cs:xmmword_1800AD720, 8
0x18005d698  jz      loc_18005D533
0x18005d69e  mov     rax, [rdi+8]
0x18005d6a2  movzx   ebx, byte ptr [rax+71h]
0x18005d6a6  call    WaIsNameResolutionHandleRequired
0x18005d6ab  mov     r9d, eax
0x18005d6ae  mov     eax, [rbp+57h+var_90.ai_family]
0x18005d6b1  mov     dword ptr [rsp+0F0h+lpCompletionRoutine], eax
0x18005d6b5  mov     eax, [rbp+57h+var_38]
0x18005d6b8  mov     dword ptr [rsp+0F0h+lpOverlapped], eax
0x18005d6bc  mov     eax, [rbp+57h+var_48]
0x18005d6bf  mov     dword ptr [rsp+0F0h+timeout], eax
0x18005d6c3  mov     eax, [rbp+57h+var_90.ai_flags]
0x18005d6c6  mov     dword ptr [rsp+0F0h+ppResult], eax
0x18005d6ca  mov     dword ptr [rsp+0F0h+hints], ebx
0x18005d6ce  call    WPP_SF_llDDDD
0x18005d6d3  jmp     short loc_18005D703
0x18005d6d5  mov     rax, [rdi+8]
0x18005d6d9  movzx   ebx, byte ptr [rax+71h]
0x18005d6dd  call    WaIsNameResolutionHandleRequired
0x18005d6e2  mov     r9d, eax
0x18005d6e5  mov     eax, [rbp+57h+var_38]
0x18005d6e8  mov     dword ptr [rsp+0F0h+lpOverlapped], eax
0x18005d6ec  mov     eax, [rbp+57h+var_48]
0x18005d6ef  mov     dword ptr [rsp+0F0h+timeout], eax
0x18005d6f3  mov     eax, [rbp+57h+var_90.ai_flags]
0x18005d6f6  mov     dword ptr [rsp+0F0h+ppResult], eax
0x18005d6fa  mov     dword ptr [rsp+0F0h+hints], ebx
0x18005d6fe  call    WPP_SF_llDDD
0x18005d703  mov     ecx, [rbp+57h+var_90.ai_flags]
0x18005d706  jmp     loc_18005D533
0x18005d70b  mov     edx, eax
0x18005d70d  lea     rcx, [rbp+57h+var_A0]
0x18005d711  call    WapCompleteDnsGenericIoContext
0x18005d716  jmp     loc_18005D5B5
0x18005d71b  mov     r9d, 3
0x18005d721  lea     rdx, ThreadActionQueue
0x18005d728  mov     r8, rsi
0x18005d72b  call    McTemplateU0pq_EventWriteTransfer
0x18005d730  jmp     loc_18005D59E
```
