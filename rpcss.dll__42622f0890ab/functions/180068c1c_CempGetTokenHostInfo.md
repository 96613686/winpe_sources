# CempGetTokenHostInfo

- ea: `0x180068c1c`
- end: `0x180068e8d`
- name: `CempGetTokenHostInfo`
- size: `625`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002e29c`

## callees

- `0x180068c1c`
- `0x180068ea0`
- `0x180068ec0`
- `0x1800b27e0`
- `0x1800b3128`
- `0x18010a084`

## import_xrefs

- `ntdll!RtlCopySid` at `0x180068e25`
- `ntdll!RtlCopySid` at `0x180068e25`
- `ntdll!RtlLengthSid` at `0x180068d21`
- `ntdll!RtlLengthSid` at `0x180068d21`
- `ntdll!NtQueryInformationToken` at `0x180068cb3`
- `ntdll!NtQueryInformationToken` at `0x180068cf9`
- `ntdll!NtQueryInformationToken` at `0x180068d57`
- `ntdll!NtQueryInformationToken` at `0x180068cb3`
- `ntdll!NtQueryInformationToken` at `0x180068cf9`
- `ntdll!NtQueryInformationToken` at `0x180068d57`
- `ntdll!RtlQueryTokenHostIdAsUlong64` at `0x180068d9a`
- `ntdll!RtlQueryTokenHostIdAsUlong64` at `0x180068d9a`
- `api-ms-win-core-psm-key-l1-1-0!PsmGetKeyFromToken` at `0x180068c8b`
- `api-ms-win-core-psm-key-l1-1-0!PsmGetKeyFromToken` at `0x180068c8b`
- `ext-ms-win-com-psmregister-l1-1-0!PsmQueryBackgroundActivationType` at `0x180068d6f`
- `ext-ms-win-com-psmregister-l1-1-0!PsmQueryBackgroundActivationType` at `0x180068d6f`

## pseudocode

```c
__int64 __fastcall CempGetTokenHostInfo(HANDLE TokenHandle, char *a2)
{
  NTSTATUS KeyFromToken; // ebx
  void **v5; // rsi
  void *v6; // rbx
  ULONG v7; // eax
  __int64 v8; // rbx
  int v9; // edi
  int v10; // r15d
  __int64 v11; // rdx
  _WORD *v12; // r9
  __int64 v13; // r8
  _WORD *v14; // rax
  _WORD *v15; // rdx
  ULONG TokenInformationLength; // [rsp+30h] [rbp-D0h] BYREF
  int v18; // [rsp+34h] [rbp-CCh] BYREF
  int v19; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v20[464]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE SourceSid[68]; // [rsp+210h] [rbp+110h] BYREF
  int TokenInformation; // [rsp+254h] [rbp+154h] BYREF
  int v23; // [rsp+258h] [rbp+158h]
  __int64 v24; // [rsp+260h] [rbp+160h] BYREF

  v18 = 0;
  TokenInformationLength = 0;
  memset_0(v20, 0, 0x228u);
  v19 = 464;
  KeyFromToken = PsmGetKeyFromToken(TokenHandle, v20, &v19, 0);
  if ( KeyFromToken >= 0 )
  {
    KeyFromToken = NtQueryInformationToken(TokenHandle, TokenUser, 0, 0, &TokenInformationLength);
    if ( (int)(KeyFromToken + 0x80000000) < 0 || KeyFromToken == -1073741789 )
    {
      v5 = (void **)SafeAllocaAllocateFromHeap(TokenInformationLength);
      if ( v5 )
      {
        KeyFromToken = NtQueryInformationToken(
                         TokenHandle,
                         TokenUser,
                         v5,
                         TokenInformationLength,
                         &TokenInformationLength);
        if ( KeyFromToken >= 0 )
        {
          v6 = *v5;
          memset_0(SourceSid, 0, sizeof(SourceSid));
          v7 = RtlLengthSid(v6);
          memcpy_0(SourceSid, v6, v7);
          KeyFromToken = NtQueryInformationToken(
                           TokenHandle,
                           TokenSessionId,
                           &TokenInformation,
                           4u,
                           &TokenInformationLength);
          if ( KeyFromToken >= 0 )
          {
            KeyFromToken = PsmQueryBackgroundActivationType(TokenHandle, &v18);
            if ( KeyFromToken >= 0 )
            {
              v23 = 1 << v18;
              KeyFromToken = RtlQueryTokenHostIdAsUlong64(TokenHandle, &v24);
              if ( KeyFromToken >= 0 )
              {
                v8 = v24;
                v9 = v23;
                v10 = TokenInformation;
                memset_0(a2, 0, 0x228u);
                v11 = 2147483646;
                v12 = v20;
                v13 = 232;
                v14 = a2;
                do
                {
                  if ( !v11 )
                    break;
                  if ( !*v12 )
                    break;
                  *v14++ = *v12++;
                  --v11;
                  --v13;
                }
                while ( v13 );
                v15 = v14 - 1;
                if ( v13 )
                  v15 = v14;
                *v15 = 0;
                RtlCopySid(0x44u, a2 + 464, SourceSid);
                *((_QWORD *)a2 + 68) = v8;
                KeyFromToken = 0;
                *((_DWORD *)a2 + 133) = v10;
                *((_DWORD *)a2 + 134) = v9;
              }
            }
          }
        }
        CempHeapFree(v5);
      }
      else
      {
        return (unsigned int)-1073741801;
      }
    }
  }
  return (unsigned int)KeyFromToken;
}

```

## disassembly

```asm
0x180068c1c  mov     [rsp-8+arg_10], rbx
0x180068c21  mov     [rsp-8+arg_18], rsi
0x180068c26  push    rbp
0x180068c27  push    rdi
0x180068c28  push    r12
0x180068c2a  push    r14
0x180068c2c  push    r15
0x180068c2e  lea     rbp, [rsp-180h]
0x180068c36  sub     rsp, 280h
0x180068c3d  mov     rax, cs:__security_cookie
0x180068c44  xor     rax, rsp
0x180068c47  mov     [rbp+1A0h+var_30], rax
0x180068c4e  mov     r14, rdx
0x180068c51  mov     rdi, rcx
0x180068c54  xor     r12d, r12d
0x180068c57  lea     rcx, [rsp+2A0h+var_260]; void *
0x180068c5c  xor     edx, edx; Val
0x180068c5e  mov     [rsp+2A0h+var_26C], r12d
0x180068c63  mov     r8d, 228h; Size
0x180068c69  mov     [rsp+2A0h+TokenInformationLength], r12d
0x180068c6e  call    memset_0
0x180068c73  xor     r9d, r9d
0x180068c76  mov     [rsp+2A0h+var_268], 1D0h
0x180068c7e  lea     r8, [rsp+2A0h+var_268]
0x180068c83  mov     rcx, rdi
0x180068c86  lea     rdx, [rsp+2A0h+var_260]
0x180068c8b  call    cs:__imp_PsmGetKeyFromToken
0x180068c91  mov     ebx, eax
0x180068c93  test    eax, eax
0x180068c95  js      loc_180068E4B
0x180068c9b  lea     rax, [rsp+2A0h+TokenInformationLength]
0x180068ca0  xor     r9d, r9d; TokenInformationLength
0x180068ca3  xor     r8d, r8d; TokenInformation
0x180068ca6  mov     [rsp+2A0h+ReturnLength], rax; ReturnLength
0x180068cab  lea     edx, [r12+1]; TokenInformationClass
0x180068cb0  mov     rcx, rdi; TokenHandle
0x180068cb3  call    cs:__imp_NtQueryInformationToken
0x180068cb9  mov     ecx, 80000000h
0x180068cbe  mov     ebx, eax
0x180068cc0  add     eax, ecx
0x180068cc2  test    ecx, eax
0x180068cc4  jz      loc_180068E78
0x180068cca  mov     ecx, [rsp+2A0h+TokenInformationLength]
0x180068cce  call    SafeAllocaAllocateFromHeap
0x180068cd3  mov     rsi, rax
0x180068cd6  test    rax, rax
0x180068cd9  jz      loc_180068E86
0x180068cdf  mov     r9d, [rsp+2A0h+TokenInformationLength]; TokenInformationLength
0x180068ce4  lea     rax, [rsp+2A0h+TokenInformationLength]
0x180068ce9  mov     r8, rsi; TokenInformation
0x180068cec  mov     [rsp+2A0h+ReturnLength], rax; ReturnLength
0x180068cf1  mov     edx, 1; TokenInformationClass
0x180068cf6  mov     rcx, rdi; TokenHandle
0x180068cf9  call    cs:__imp_NtQueryInformationToken
0x180068cff  mov     ebx, eax
0x180068d01  test    eax, eax
0x180068d03  js      loc_180068E43
0x180068d09  mov     rbx, [rsi]
0x180068d0c  lea     rcx, [rbp+1A0h+SourceSid]; void *
0x180068d13  xor     edx, edx; Val
0x180068d15  lea     r8d, [rdx+44h]; Size
0x180068d19  call    memset_0
0x180068d1e  mov     rcx, rbx; Sid
0x180068d21  call    cs:__imp_RtlLengthSid
0x180068d27  mov     r8d, eax; Size
0x180068d2a  mov     rdx, rbx; Src
0x180068d2d  lea     rcx, [rbp+1A0h+SourceSid]; void *
0x180068d34  call    memcpy_0
0x180068d39  mov     r9d, 4; TokenInformationLength
0x180068d3f  lea     rax, [rsp+2A0h+TokenInformationLength]
0x180068d44  lea     r8, [rbp+1A0h+TokenInformation]; TokenInformation
0x180068d4b  mov     [rsp+2A0h+ReturnLength], rax; ReturnLength
0x180068d50  mov     rcx, rdi; TokenHandle
0x180068d53  lea     edx, [r9+8]; TokenInformationClass
0x180068d57  call    cs:__imp_NtQueryInformationToken
0x180068d5d  mov     ebx, eax
0x180068d5f  test    eax, eax
0x180068d61  js      loc_180068E43
0x180068d67  lea     rdx, [rsp+2A0h+var_26C]
0x180068d6c  mov     rcx, rdi
0x180068d6f  call    cs:__imp_PsmQueryBackgroundActivationType
0x180068d75  mov     ebx, eax
0x180068d77  test    eax, eax
0x180068d79  js      loc_180068E43
0x180068d7f  mov     ecx, [rsp+2A0h+var_26C]
0x180068d83  lea     rdx, [rbp+1A0h+var_40]
0x180068d8a  mov     eax, 1
0x180068d8f  shl     eax, cl
0x180068d91  mov     rcx, rdi
0x180068d94  mov     [rbp+1A0h+var_48], eax
0x180068d9a  call    cs:__imp_RtlQueryTokenHostIdAsUlong64
0x180068da0  mov     ebx, eax
0x180068da2  test    eax, eax
0x180068da4  js      loc_180068E43
0x180068daa  mov     rbx, [rbp+1A0h+var_40]
0x180068db1  xor     edx, edx; Val
0x180068db3  mov     edi, [rbp+1A0h+var_48]
0x180068db9  mov     r8d, 228h; Size
0x180068dbf  mov     r15d, [rbp+1A0h+TokenInformation]
0x180068dc6  mov     rcx, r14; void *
0x180068dc9  call    memset_0
0x180068dce  mov     edx, 7FFFFFFEh
0x180068dd3  lea     r9, [rsp+2A0h+var_260]
0x180068dd8  mov     r8d, 0E8h
0x180068dde  mov     rax, r14
0x180068de1  test    rdx, rdx
0x180068de4  jz      short loc_180068E03
0x180068de6  movzx   ecx, word ptr [r9]
0x180068dea  test    cx, cx
0x180068ded  jz      short loc_180068E03
0x180068def  mov     [rax], cx
0x180068df2  add     r9, 2
0x180068df6  add     rax, 2
0x180068dfa  dec     rdx
0x180068dfd  sub     r8, 1
0x180068e01  jnz     short loc_180068DE1
0x180068e03  test    r8, r8
0x180068e06  lea     rdx, [rax-2]
0x180068e0a  lea     r8, [rbp+1A0h+SourceSid]; SourceSid
0x180068e11  mov     ecx, 44h ; 'D'; DestinationSidLength
0x180068e16  cmovnz  rdx, rax
0x180068e1a  mov     [rdx], r12w
0x180068e1e  lea     rdx, [r14+1D0h]; DestinationSid
0x180068e25  call    cs:__imp_RtlCopySid
0x180068e2b  mov     [r14+220h], rbx
0x180068e32  mov     ebx, r12d
0x180068e35  mov     [r14+214h], r15d
0x180068e3c  mov     [r14+218h], edi
0x180068e43  mov     rcx, rsi
0x180068e46  call    CempHeapFree
0x180068e4b  mov     eax, ebx
0x180068e4d  mov     rcx, [rbp+1A0h+var_30]
0x180068e54  xor     rcx, rsp; StackCookie
0x180068e57  call    __security_check_cookie
0x180068e5c  lea     r11, [rsp+2A0h+var_20]
0x180068e64  mov     rbx, [r11+40h]
0x180068e68  mov     rsi, [r11+48h]
0x180068e6c  mov     rsp, r11
0x180068e6f  pop     r15
0x180068e71  pop     r14
0x180068e73  pop     r12
0x180068e75  pop     rdi
0x180068e76  pop     rbp
0x180068e77  retn
0x180068e78  cmp     ebx, 0C0000023h
0x180068e7e  jz      loc_180068CCA
0x180068e84  jmp     short loc_180068E4B
0x180068e86  mov     ebx, 0C0000017h
0x180068e8b  jmp     short loc_180068E4B
```
