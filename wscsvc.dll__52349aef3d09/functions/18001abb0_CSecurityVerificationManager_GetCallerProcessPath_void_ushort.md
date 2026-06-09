# CSecurityVerificationManager::GetCallerProcessPath(void *,ushort * *)

- ea: `0x18001abb0`
- end: `0x18001aed8`
- name: `?GetCallerProcessPath@CSecurityVerificationManager@@SAJPEAXPEAPEAG@Z`
- size: `808`
- prototype: `__int64 __fastcall(void *, unsigned __int16 **)`
- caller_count: `7`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180005308`
- `0x18001aa90`
- `0x180025520`
- `0x180031e24`
- `0x180031efc`
- `0x18003532c`
- `0x1800356b4`

## callees

- `0x180008e48`
- `0x18001abb0`
- `0x1800202e8`
- `0x180029e74`
- `0x18002b1ac`
- `0x18002fbb4`
- `0x18003fc30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ade8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001adff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ade8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001adff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ad2d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001addd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ad2d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001addd`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18001ac37`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18001ac37`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18001ad5e`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18001ad5e`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x18001ad8b`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x18001ad8b`

## pseudocode

```c
__int64 __fastcall CSecurityVerificationManager::GetCallerProcessPath(void *a1, unsigned __int16 **a2)
{
  int v3; // ebx
  unsigned __int64 v5; // rax
  unsigned __int64 v6; // rbx
  size_t v7; // rax
  unsigned __int16 *v8; // rsi
  __int64 v9; // rax
  WCHAR *v10; // rdx
  unsigned __int16 *v11; // r8
  unsigned __int16 *v12; // rcx
  unsigned __int16 v13; // di
  HANDLE v14; // rax
  void *v15; // rbp
  __int64 v16; // rax
  DWORD LastError; // eax
  DWORD dwSize[4]; // [rsp+30h] [rbp-2C8h] BYREF
  int RpcCallAttributes; // [rsp+40h] [rbp-2B8h] BYREF
  __int64 v20; // [rsp+44h] [rbp-2B4h]
  int v21; // [rsp+4Ch] [rbp-2ACh]
  __int128 v22; // [rsp+50h] [rbp-2A8h]
  __int128 v23; // [rsp+60h] [rbp-298h]
  __int128 v24; // [rsp+70h] [rbp-288h]
  DWORD dwProcessId[4]; // [rsp+80h] [rbp-278h]
  __int128 v26; // [rsp+90h] [rbp-268h]
  __int128 v27; // [rsp+A0h] [rbp-258h]
  __int64 v28; // [rsp+B0h] [rbp-248h]
  WCHAR ExeName[264]; // [rsp+C0h] [rbp-238h] BYREF

  if ( a1 && a2 )
  {
    RpcCallAttributes = 2;
    v21 = 0;
    v22 = 0;
    v20 = 16;
    v23 = 0;
    v24 = 0;
    *(_OWORD *)dwProcessId = 0;
    v26 = 0;
    v27 = 0;
    v28 = 0;
    v3 = RpcServerInqCallAttributesW(a1, &RpcCallAttributes);
    if ( v3 )
      goto LABEL_4;
    v14 = OpenProcess(0x1000u, 0, dwProcessId[0]);
    v15 = v14;
    if ( v14 )
    {
      v6 = 260;
      dwSize[0] = 260;
      if ( !QueryFullProcessImageNameW(v14, 0, ExeName, dwSize) )
      {
        LastError = GetLastError();
        if ( !LastError )
          LastError = 3;
        v3 = LastError;
        goto LABEL_21;
      }
      if ( dwSize[0] )
      {
        if ( dwSize[0] > 0x103 )
        {
          v3 = 111;
        }
        else
        {
          v16 = -1;
          do
            ++v16;
          while ( ExeName[v16] );
          v5 = v16 + 1;
          if ( v5 >= 0x104 )
          {
            if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            {
              WPP_SF_dd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                10,
                WPP_bc50b57d3a7f3ca15f27abc6215da79e_Traceguids,
                (unsigned int)v5,
                260);
            }
          }
          else
          {
            v6 = v5;
          }
          v7 = 2 * v6;
          if ( !is_mul_ok(v6, 2u) )
            v7 = -1;
          v8 = (unsigned __int16 *)operator new[](v7, (const struct std::nothrow_t *)&std::nothrow);
          if ( v8 )
          {
            if ( v6 )
            {
              v9 = 2147483646;
              v10 = ExeName;
              v11 = v8;
              do
              {
                if ( !v9 )
                  break;
                if ( !*v10 )
                  break;
                *v11++ = *v10++;
                --v9;
                --v6;
              }
              while ( v6 );
              v12 = v11 - 1;
              if ( v6 )
                v12 = v11;
              *v12 = 0;
              *a2 = v8;
              v13 = 0;
            }
            else
            {
              v13 = 87;
              if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  11,
                  WPP_bc50b57d3a7f3ca15f27abc6215da79e_Traceguids,
                  2147942487LL);
              }
              operator delete(v8);
            }
          }
          else
          {
            if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_bc50b57d3a7f3ca15f27abc6215da79e_Traceguids);
            }
            v13 = 14;
          }
          v3 = v13;
        }
LABEL_21:
        CloseHandle(v15);
        goto LABEL_4;
      }
      v3 = 3;
      CloseHandle(v15);
    }
    else
    {
      v3 = GetLastError();
      if ( !v3 )
      {
        LOWORD(v3) = 110;
        return (unsigned __int16)v3 | 0x80070000;
      }
    }
LABEL_4:
    if ( v3 <= 0 )
      return (unsigned int)v3;
    return (unsigned __int16)v3 | 0x80070000;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x18001abb0  mov     r11, rsp
0x18001abb3  push    rdi
0x18001abb4  sub     rsp, 2F0h
0x18001abbb  mov     rax, cs:__security_cookie
0x18001abc2  xor     rax, rsp
0x18001abc5  mov     [rsp+2F8h+var_28], rax
0x18001abcd  mov     rdi, rdx
0x18001abd0  test    rcx, rcx
0x18001abd3  jz      loc_18001AC7A
0x18001abd9  test    rdx, rdx
0x18001abdc  jz      loc_18001AC7A
0x18001abe2  xorps   xmm0, xmm0
0x18001abe5  mov     [r11+18h], rbx
0x18001abe9  xor     eax, eax
0x18001abeb  mov     [rsp+2F8h+RpcCallAttributes], 2
0x18001abf3  mov     [rsp+2F8h+var_2AC], eax
0x18001abf7  lea     rdx, [rsp+2F8h+RpcCallAttributes]; RpcCallAttributes
0x18001abfc  movups  [rsp+2F8h+var_2A8], xmm0
0x18001ac01  mov     [rsp+2F8h+var_2B4], 10h
0x18001ac0a  movups  [rsp+2F8h+var_298], xmm0
0x18001ac0f  mov     [r11+20h], rbp
0x18001ac13  movups  [rsp+2F8h+var_288], xmm0
0x18001ac18  movups  xmmword ptr [rsp+2F8h+dwProcessId], xmm0
0x18001ac20  movups  [rsp+2F8h+var_268], xmm0
0x18001ac28  movups  [rsp+2F8h+var_258], xmm0
0x18001ac30  mov     [r11-248h], rax
0x18001ac37  call    cs:__imp_RpcServerInqCallAttributesW
0x18001ac3d  mov     ebx, eax
0x18001ac3f  test    eax, eax
0x18001ac41  jz      loc_18001AD4F
0x18001ac47  test    ebx, ebx
0x18001ac49  jg      loc_18001AE14
0x18001ac4f  mov     rbp, [rsp+2F8h+arg_18]
0x18001ac57  mov     eax, ebx
0x18001ac59  mov     rbx, [rsp+2F8h+arg_10]
0x18001ac61  mov     rcx, [rsp+2F8h+var_28]
0x18001ac69  xor     rcx, rsp; StackCookie
0x18001ac6c  call    __security_check_cookie
0x18001ac71  add     rsp, 2F0h
0x18001ac78  pop     rdi
0x18001ac79  retn
0x18001ac7a  mov     eax, 80070057h
0x18001ac7f  jmp     short loc_18001AC61
0x18001ac81  inc     rax
0x18001ac84  lea     r14, WPP_GLOBAL_Control
0x18001ac8b  cmp     rax, rbx
0x18001ac8e  jnb     loc_18001AE2C
0x18001ac94  mov     rbx, rax
0x18001ac97  mov     eax, 2
0x18001ac9c  mul     rbx
0x18001ac9f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001aca6  cmovb   rax, rsi
0x18001acaa  mov     rcx, rax; unsigned __int64
0x18001acad  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001acb2  mov     rsi, rax
0x18001acb5  test    rax, rax
0x18001acb8  jz      short loc_18001AD38
0x18001acba  test    rbx, rbx
0x18001acbd  jz      loc_18001AE6E
0x18001acc3  cmp     rbx, 7FFFFFFFh
0x18001acca  ja      loc_18001AE67
0x18001acd0  mov     eax, 7FFFFFFEh
0x18001acd5  lea     rdx, [rsp+2F8h+ExeName]
0x18001acdd  mov     r8, rsi
0x18001ace0  test    rax, rax
0x18001ace3  jz      short loc_18001AD02
0x18001ace5  movzx   ecx, word ptr [rdx]
0x18001ace8  test    cx, cx
0x18001aceb  jz      short loc_18001AD02
0x18001aced  mov     [r8], cx
0x18001acf1  add     rdx, 2
0x18001acf5  add     r8, 2
0x18001acf9  dec     rax
0x18001acfc  sub     rbx, 1
0x18001ad00  jnz     short loc_18001ACE0
0x18001ad02  test    rbx, rbx
0x18001ad05  lea     rcx, [r8-2]
0x18001ad09  cmovnz  rcx, r8
0x18001ad0d  xor     eax, eax
0x18001ad0f  mov     [rcx], ax
0x18001ad12  mov     [rdi], rsi
0x18001ad15  xor     edi, edi
0x18001ad17  mov     r14, [rsp+2F8h+var_18]
0x18001ad1f  mov     rsi, [rsp+2F8h+var_10]
0x18001ad27  movzx   ebx, di
0x18001ad2a  mov     rcx, rbp; hObject
0x18001ad2d  call    cs:__imp_CloseHandle
0x18001ad33  jmp     loc_18001AC47
0x18001ad38  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ad3f  cmp     rcx, r14
0x18001ad42  jnz     loc_18001AEB4
0x18001ad48  mov     edi, 8007000Eh
0x18001ad4d  jmp     short loc_18001AD17
0x18001ad4f  mov     r8d, [rsp+2F8h+dwProcessId]; dwProcessId
0x18001ad57  xor     edx, edx; bInheritHandle
0x18001ad59  mov     ecx, 1000h; dwDesiredAccess
0x18001ad5e  call    cs:__imp_OpenProcess
0x18001ad64  mov     rbp, rax
0x18001ad67  test    rax, rax
0x18001ad6a  jz      loc_18001ADFF
0x18001ad70  mov     ebx, 104h
0x18001ad75  lea     r9, [rsp+2F8h+dwSize]; lpdwSize
0x18001ad7a  lea     r8, [rsp+2F8h+ExeName]; lpExeName
0x18001ad82  mov     [rsp+2F8h+dwSize], ebx
0x18001ad86  xor     edx, edx; dwFlags
0x18001ad88  mov     rcx, rax; hProcess
0x18001ad8b  call    cs:__imp_QueryFullProcessImageNameW
0x18001ad91  test    eax, eax
0x18001ad93  jz      short loc_18001ADE8
0x18001ad95  mov     eax, [rsp+2F8h+dwSize]
0x18001ad99  test    eax, eax
0x18001ad9b  jz      short loc_18001ADD5
0x18001ad9d  cmp     eax, 103h
0x18001ada2  ja      short loc_18001AE22
0x18001ada4  mov     [rsp+2F8h+var_10], rsi
0x18001adac  lea     rcx, [rsp+2F8h+ExeName]
0x18001adb4  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x18001adbb  mov     [rsp+2F8h+var_18], r14
0x18001adc3  mov     rax, rsi
0x18001adc6  inc     rax
0x18001adc9  cmp     word ptr [rcx+rax*2], 0
0x18001adce  jnz     short loc_18001ADC6
0x18001add0  jmp     loc_18001AC81
0x18001add5  mov     rcx, rbp; hObject
0x18001add8  mov     ebx, 3
0x18001addd  call    cs:__imp_CloseHandle
0x18001ade3  jmp     loc_18001AC47
0x18001ade8  call    cs:__imp_GetLastError
0x18001adee  mov     ebx, 3
0x18001adf3  test    eax, eax
0x18001adf5  cmovz   eax, ebx
0x18001adf8  mov     ebx, eax
0x18001adfa  jmp     loc_18001AD2A
0x18001adff  call    cs:__imp_GetLastError
0x18001ae05  mov     ebx, eax
0x18001ae07  test    eax, eax
0x18001ae09  jnz     loc_18001AC47
0x18001ae0f  mov     ebx, 6Eh ; 'n'
0x18001ae14  movzx   ebx, bx
0x18001ae17  or      ebx, 80070000h
0x18001ae1d  jmp     loc_18001AC4F
0x18001ae22  mov     ebx, 6Fh ; 'o'
0x18001ae27  jmp     loc_18001AD2A
0x18001ae2c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ae33  cmp     rcx, r14
0x18001ae36  jz      loc_18001AC97
0x18001ae3c  test    byte ptr [rcx+1Ch], 4
0x18001ae40  jz      loc_18001AC97
0x18001ae46  mov     rcx, [rcx+10h]
0x18001ae4a  lea     r8, WPP_bc50b57d3a7f3ca15f27abc6215da79e_Traceguids
0x18001ae51  mov     r9d, eax
0x18001ae54  mov     [rsp+2F8h+var_2D8], ebx
0x18001ae58  mov     edx, 0Ah
0x18001ae5d  call    WPP_SF_dd
0x18001ae62  jmp     loc_18001AC97
0x18001ae67  mov     edi, 80070057h
0x18001ae6c  jmp     short loc_18001AE78
0x18001ae6e  mov     edi, 80070057h
0x18001ae73  test    rbx, rbx
0x18001ae76  jz      short loc_18001AE7D
0x18001ae78  xor     eax, eax
0x18001ae7a  mov     [rsi], ax
0x18001ae7d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ae84  cmp     rcx, r14
0x18001ae87  jz      short loc_18001AEA7
0x18001ae89  test    byte ptr [rcx+1Ch], 1
0x18001ae8d  jz      short loc_18001AEA7
0x18001ae8f  mov     rcx, [rcx+10h]
0x18001ae93  lea     r8, WPP_bc50b57d3a7f3ca15f27abc6215da79e_Traceguids
0x18001ae9a  mov     edx, 0Bh
0x18001ae9f  mov     r9d, edi
0x18001aea2  call    WPP_SF_d
0x18001aea7  mov     rcx, rsi; Block
0x18001aeaa  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001aeaf  jmp     loc_18001AD17
0x18001aeb4  test    byte ptr [rcx+1Ch], 1
0x18001aeb8  jz      loc_18001AD48
0x18001aebe  mov     rcx, [rcx+10h]
0x18001aec2  lea     r8, WPP_bc50b57d3a7f3ca15f27abc6215da79e_Traceguids
0x18001aec9  mov     edx, 0Ch
0x18001aece  call    WPP_SF_
0x18001aed3  jmp     loc_18001AD48
```
