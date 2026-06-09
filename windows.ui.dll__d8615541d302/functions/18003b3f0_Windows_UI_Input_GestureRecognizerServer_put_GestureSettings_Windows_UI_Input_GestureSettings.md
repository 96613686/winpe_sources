# Windows::UI::Input::GestureRecognizerServer::put_GestureSettings(Windows::UI::Input::GestureSettings)

- ea: `0x18003b3f0`
- end: `0x18003b642`
- name: `?put_GestureSettings@GestureRecognizerServer@Input@UI@Windows@@UEAAJW4GestureSettings@234@@Z`
- size: `594`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x18003b3f0`
- `0x18003b648`
- `0x1800c73c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003b41d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003b41d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003b55a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003b5db`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003b55a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003b5db`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18003b5cd`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18003b5cd`
- `NInput!SetInteractionConfigurationInteractionContext` at `0x18003b538`
- `NInput!SetInteractionConfigurationInteractionContext` at `0x18003b538`
- `NInput!GetInteractionConfigurationInteractionContext` at `0x18003b50b`
- `NInput!GetInteractionConfigurationInteractionContext` at `0x18003b50b`

## pseudocode

```c
__int64 __fastcall Windows::UI::Input::GestureRecognizerServer::put_GestureSettings(__int64 a1, int a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rsi
  int v5; // eax
  int v6; // eax
  int v7; // eax
  __int64 v8; // rcx
  int InteractionConfigurationInteractionContext; // edi
  int v10; // edx
  int v11; // edx
  int v13; // eax
  int v14; // eax
  __m128i si128; // [rsp+20h] [rbp-48h] BYREF
  __m128i v16; // [rsp+30h] [rbp-38h]
  __m128i v17; // [rsp+40h] [rbp-28h] BYREF

  v2 = (struct _RTL_CRITICAL_SECTION *)(a1 + 584);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 584));
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v17 = _mm_load_si128((const __m128i *)&_xmm);
  v16 = _mm_load_si128((const __m128i *)&_xmm);
  if ( (a2 & 0xFFFE0000) != 0 )
  {
    RoOriginateErrorW(2147942487LL, 0, 0);
    if ( v2 )
      LeaveCriticalSection(v2);
    return 2147942487LL;
  }
  else
  {
    if ( (a2 & 0x17FC0) != 0 )
    {
      v5 = 1;
      if ( (a2 & 0x40) != 0 )
        v5 = 3;
      si128.m128i_i32[1] = v5;
      if ( (a2 & 0x80u) != 0 )
      {
        v5 |= 4u;
        si128.m128i_i32[1] = v5;
      }
      if ( (a2 & 0x100) != 0 )
      {
        v5 |= 0x102u;
        si128.m128i_i32[1] = v5;
      }
      if ( (a2 & 0x200) != 0 )
      {
        v5 |= 0x204u;
        si128.m128i_i32[1] = v5;
      }
      if ( (a2 & 0x400) != 0 )
      {
        v5 |= 8u;
        si128.m128i_i32[1] = v5;
      }
      if ( (a2 & 0x800) != 0 )
      {
        v5 |= 0x10u;
        si128.m128i_i32[1] = v5;
      }
      if ( (a2 & 0x1000) != 0 )
      {
        v5 |= 0x20u;
        si128.m128i_i32[1] = v5;
      }
      if ( (a2 & 0x2000) != 0 )
      {
        v5 |= 0x40u;
        si128.m128i_i32[1] = v5;
      }
      if ( (a2 & 0x4000) != 0 )
      {
        v5 |= 0x80u;
        si128.m128i_i32[1] = v5;
      }
      if ( (a2 & 0x10000) != 0 )
        si128.m128i_i32[1] = v5 | 0x800;
    }
    if ( (a2 & 3) != 0 )
    {
      v13 = 1;
      if ( (a2 & 2) != 0 )
        v13 = 3;
      si128.m128i_i32[3] = v13;
      if ( (a2 & 1) != 0 )
        si128.m128i_i32[3] = v13 | 4;
    }
    v6 = v16.m128i_i32[1];
    if ( (a2 & 0x10) != 0 )
      v6 = 1;
    v16.m128i_i32[1] = v6;
    if ( (a2 & 0xC) != 0 )
    {
      v14 = 1;
      if ( (a2 & 8) != 0 )
        v14 = 3;
      v16.m128i_i32[3] = v14;
      if ( (a2 & 4) != 0 )
        v16.m128i_i32[3] = v14 | 4;
    }
    v7 = v17.m128i_i32[1];
    v8 = *(_QWORD *)(a1 + 296);
    if ( (a2 & 0x20) != 0 )
      v7 = 1;
    v17.m128i_i32[1] = v7;
    InteractionConfigurationInteractionContext = GetInteractionConfigurationInteractionContext(v8, 1, &v17.m128i_u64[1]);
    TouchWinRT::OnErrorOriginateError((TouchWinRT *)(unsigned int)InteractionConfigurationInteractionContext, v10);
    if ( InteractionConfigurationInteractionContext >= 0 )
    {
      if ( (a2 & 0x8000) != 0 )
        v17.m128i_i32[3] |= 1u;
      else
        v17.m128i_i32[3] &= ~1u;
      InteractionConfigurationInteractionContext = SetInteractionConfigurationInteractionContext(
                                                     *(_QWORD *)(a1 + 296),
                                                     6,
                                                     &si128);
      TouchWinRT::OnErrorOriginateError((TouchWinRT *)(unsigned int)InteractionConfigurationInteractionContext, v11);
      if ( InteractionConfigurationInteractionContext >= 0 )
        *(_DWORD *)(a1 + 480) = a2;
    }
    if ( v2 )
      LeaveCriticalSection(v2);
    return (unsigned int)InteractionConfigurationInteractionContext;
  }
}

```

## disassembly

```asm
0x18003b3f0  push    rbp
0x18003b3f2  push    rbx
0x18003b3f3  push    rsi
0x18003b3f4  push    rdi
0x18003b3f5  push    r14
0x18003b3f7  push    r15
0x18003b3f9  mov     rbp, rsp
0x18003b3fc  sub     rsp, 68h
0x18003b400  mov     rax, cs:__security_cookie
0x18003b407  xor     rax, rsp
0x18003b40a  mov     [rbp+var_18], rax
0x18003b40e  lea     rsi, [rcx+248h]
0x18003b415  mov     r14, rcx
0x18003b418  mov     rcx, rsi; lpCriticalSection
0x18003b41b  mov     ebx, edx
0x18003b41d  call    cs:__imp_EnterCriticalSection
0x18003b423  movdqa  xmm0, cs:__xmm@00000000000000020000000000000001
0x18003b42b  movdqa  xmm1, cs:__xmm@00000000000000040000000000000003
0x18003b433  movdqu  [rbp+var_48], xmm0
0x18003b438  movdqa  xmm0, cs:__xmm@00000000000000060000000000000005
0x18003b440  movdqu  [rbp+var_28], xmm0
0x18003b445  movdqu  [rbp+var_38], xmm1
0x18003b44a  test    ebx, 0FFFE0000h
0x18003b450  jnz     loc_18003B5C1
0x18003b456  mov     edx, 3
0x18003b45b  lea     r15d, [rdx-2]
0x18003b45f  test    ebx, 17FC0h
0x18003b465  jz      short loc_18003B4D2
0x18003b467  test    bl, 40h
0x18003b46a  mov     eax, r15d
0x18003b46d  cmovnz  eax, edx
0x18003b470  mov     dword ptr [rbp+var_48+4], eax
0x18003b473  test    bl, bl
0x18003b475  js      loc_18003B5E8
0x18003b47b  bt      ebx, 8
0x18003b47f  jnb     short loc_18003B489
0x18003b481  or      eax, 102h
0x18003b486  mov     dword ptr [rbp+var_48+4], eax
0x18003b489  bt      ebx, 9
0x18003b48d  jb      loc_18003B5F3
0x18003b493  bt      ebx, 0Ah
0x18003b497  jb      loc_18003B600
0x18003b49d  mov     ecx, 800h
0x18003b4a2  test    ecx, ebx
0x18003b4a4  jnz     loc_18003B60B
0x18003b4aa  bt      ebx, 0Ch
0x18003b4ae  jb      loc_18003B616
0x18003b4b4  bt      ebx, 0Dh
0x18003b4b8  jb      loc_18003B621
0x18003b4be  bt      ebx, 0Eh
0x18003b4c2  jb      loc_18003B62C
0x18003b4c8  bt      ebx, 10h
0x18003b4cc  jb      loc_18003B638
0x18003b4d2  test    dl, bl
0x18003b4d4  jnz     loc_18003B57B
0x18003b4da  mov     eax, dword ptr [rbp+var_38+4]
0x18003b4dd  test    bl, 10h
0x18003b4e0  cmovnz  eax, r15d
0x18003b4e4  mov     dword ptr [rbp+var_38+4], eax
0x18003b4e7  test    bl, 0Ch
0x18003b4ea  jnz     loc_18003B5A1
0x18003b4f0  mov     eax, dword ptr [rbp+var_28+4]
0x18003b4f3  lea     r8, [rbp+var_28+8]
0x18003b4f7  mov     rcx, [r14+128h]
0x18003b4fe  test    bl, 20h
0x18003b501  mov     edx, r15d
0x18003b504  cmovnz  eax, r15d
0x18003b508  mov     dword ptr [rbp+var_28+4], eax
0x18003b50b  call    cs:__imp_GetInteractionConfigurationInteractionContext
0x18003b511  mov     ecx, eax; this
0x18003b513  mov     edi, eax
0x18003b515  call    ?OnErrorOriginateError@TouchWinRT@@YAJJ@Z; TouchWinRT::OnErrorOriginateError(long)
0x18003b51a  test    edi, edi
0x18003b51c  js      short loc_18003B552
0x18003b51e  bt      ebx, 0Fh
0x18003b522  jnb     short loc_18003B59B
0x18003b524  or      dword ptr [rbp+var_28+0Ch], r15d
0x18003b528  mov     rcx, [r14+128h]
0x18003b52f  lea     r8, [rbp+var_48]
0x18003b533  mov     edx, 6
0x18003b538  call    cs:__imp_SetInteractionConfigurationInteractionContext
0x18003b53e  mov     ecx, eax; this
0x18003b540  mov     edi, eax
0x18003b542  call    ?OnErrorOriginateError@TouchWinRT@@YAJJ@Z; TouchWinRT::OnErrorOriginateError(long)
0x18003b547  test    edi, edi
0x18003b549  js      short loc_18003B552
0x18003b54b  mov     [r14+1E0h], ebx
0x18003b552  test    rsi, rsi
0x18003b555  jz      short loc_18003B560
0x18003b557  mov     rcx, rsi; lpCriticalSection
0x18003b55a  call    cs:__imp_LeaveCriticalSection
0x18003b560  mov     eax, edi
0x18003b562  mov     rcx, [rbp+var_18]
0x18003b566  xor     rcx, rsp; StackCookie
0x18003b569  call    __security_check_cookie
0x18003b56e  add     rsp, 68h
0x18003b572  pop     r15
0x18003b574  pop     r14
0x18003b576  pop     rdi
0x18003b577  pop     rsi
0x18003b578  pop     rbx
0x18003b579  pop     rbp
0x18003b57a  retn
0x18003b57b  test    bl, 2
0x18003b57e  mov     eax, r15d
0x18003b581  cmovnz  eax, edx
0x18003b584  mov     dword ptr [rbp+var_48+0Ch], eax
0x18003b587  test    r15b, bl
0x18003b58a  jz      loc_18003B4DA
0x18003b590  or      eax, 4
0x18003b593  mov     dword ptr [rbp+var_48+0Ch], eax
0x18003b596  jmp     loc_18003B4DA
0x18003b59b  and     dword ptr [rbp+var_28+0Ch], 0FFFFFFFEh
0x18003b59f  jmp     short loc_18003B528
0x18003b5a1  test    bl, 8
0x18003b5a4  mov     eax, r15d
0x18003b5a7  cmovnz  eax, edx
0x18003b5aa  mov     dword ptr [rbp+var_38+0Ch], eax
0x18003b5ad  test    bl, 4
0x18003b5b0  jz      loc_18003B4F0
0x18003b5b6  or      eax, 4
0x18003b5b9  mov     dword ptr [rbp+var_38+0Ch], eax
0x18003b5bc  jmp     loc_18003B4F0
0x18003b5c1  mov     ebx, 80070057h
0x18003b5c6  xor     r8d, r8d
0x18003b5c9  mov     ecx, ebx
0x18003b5cb  xor     edx, edx
0x18003b5cd  call    cs:__imp_RoOriginateErrorW
0x18003b5d3  test    rsi, rsi
0x18003b5d6  jz      short loc_18003B5E1
0x18003b5d8  mov     rcx, rsi; lpCriticalSection
0x18003b5db  call    cs:__imp_LeaveCriticalSection
0x18003b5e1  mov     eax, ebx
0x18003b5e3  jmp     loc_18003B562
0x18003b5e8  or      eax, 4
0x18003b5eb  mov     dword ptr [rbp+var_48+4], eax
0x18003b5ee  jmp     loc_18003B47B
0x18003b5f3  or      eax, 204h
0x18003b5f8  mov     dword ptr [rbp+var_48+4], eax
0x18003b5fb  jmp     loc_18003B493
0x18003b600  or      eax, 8
0x18003b603  mov     dword ptr [rbp+var_48+4], eax
0x18003b606  jmp     loc_18003B49D
0x18003b60b  or      eax, 10h
0x18003b60e  mov     dword ptr [rbp+var_48+4], eax
0x18003b611  jmp     loc_18003B4AA
0x18003b616  or      eax, 20h
0x18003b619  mov     dword ptr [rbp+var_48+4], eax
0x18003b61c  jmp     loc_18003B4B4
0x18003b621  or      eax, 40h
0x18003b624  mov     dword ptr [rbp+var_48+4], eax
0x18003b627  jmp     loc_18003B4BE
0x18003b62c  bts     eax, 7
0x18003b630  mov     dword ptr [rbp+var_48+4], eax
0x18003b633  jmp     loc_18003B4C8
0x18003b638  or      eax, ecx
0x18003b63a  mov     dword ptr [rbp+var_48+4], eax
0x18003b63d  jmp     loc_18003B4D2
```
