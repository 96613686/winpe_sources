# CempGetTokenHostInfo

- ea: `0x18006db5c`
- end: `0x18006ddfe`
- name: `CempGetTokenHostInfo`
- size: `674`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180023a00`

## callees

- `0x18006db5c`
- `0x18006de10`
- `0x18006de40`
- `0x1800b7ac0`
- `0x1800b8428`
- `0x180112d84`

## import_xrefs

- `ntdll!RtlCopySid` at `0x18006dd8f`
- `ntdll!RtlCopySid` at `0x18006dd8f`
- `ntdll!RtlLengthSid` at `0x18006dc73`
- `ntdll!RtlLengthSid` at `0x18006dc73`
- `ntdll!NtQueryInformationToken` at `0x18006dbf9`
- `ntdll!NtQueryInformationToken` at `0x18006dc45`
- `ntdll!NtQueryInformationToken` at `0x18006dcaf`
- `ntdll!NtQueryInformationToken` at `0x18006dbf9`
- `ntdll!NtQueryInformationToken` at `0x18006dc45`
- `ntdll!NtQueryInformationToken` at `0x18006dcaf`
- `ntdll!RtlQueryTokenHostIdAsUlong64` at `0x18006dcfe`
- `ntdll!RtlQueryTokenHostIdAsUlong64` at `0x18006dcfe`
- `api-ms-win-core-psm-key-l1-1-0!PsmGetKeyFromToken` at `0x18006dbcb`
- `api-ms-win-core-psm-key-l1-1-0!PsmGetKeyFromToken` at `0x18006dbcb`
- `ext-ms-win-com-psmregister-l1-1-0!PsmQueryBackgroundActivationType` at `0x18006dccd`
- `ext-ms-win-com-psmregister-l1-1-0!PsmQueryBackgroundActivationType` at `0x18006dccd`

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
0x18006db5c  mov     [rsp-8+arg_10], rbx
0x18006db61  mov     [rsp-8+arg_18], rsi
0x18006db66  push    rbp
0x18006db67  push    rdi
0x18006db68  push    r12
0x18006db6a  push    r14
0x18006db6c  push    r15
0x18006db6e  lea     rbp, [rsp-180h]
0x18006db76  sub     rsp, 280h
0x18006db7d  mov     rax, cs:__security_cookie
0x18006db84  xor     rax, rsp
0x18006db87  mov     [rbp+1A0h+var_30], rax
0x18006db8e  mov     r14, rdx
0x18006db91  mov     rdi, rcx
0x18006db94  xor     r12d, r12d
0x18006db97  lea     rcx, [rsp+2A0h+var_260]; void *
0x18006db9c  xor     edx, edx; Val
0x18006db9e  mov     [rsp+2A0h+var_26C], r12d
0x18006dba3  mov     r8d, 228h; Size
0x18006dba9  mov     [rsp+2A0h+TokenInformationLength], r12d
0x18006dbae  call    memset_0
0x18006dbb3  xor     r9d, r9d
0x18006dbb6  mov     [rsp+2A0h+var_268], 1D0h
0x18006dbbe  lea     r8, [rsp+2A0h+var_268]
0x18006dbc3  mov     rcx, rdi
0x18006dbc6  lea     rdx, [rsp+2A0h+var_260]
0x18006dbcb  call    cs:__imp_PsmGetKeyFromToken
0x18006dbd2  nop     dword ptr [rax+rax+00h]
0x18006dbd7  mov     ebx, eax
0x18006dbd9  test    eax, eax
0x18006dbdb  js      loc_18006DDBB
0x18006dbe1  lea     rax, [rsp+2A0h+TokenInformationLength]
0x18006dbe6  xor     r9d, r9d; TokenInformationLength
0x18006dbe9  xor     r8d, r8d; TokenInformation
0x18006dbec  mov     [rsp+2A0h+ReturnLength], rax; ReturnLength
0x18006dbf1  lea     edx, [r12+1]; TokenInformationClass
0x18006dbf6  mov     rcx, rdi; TokenHandle
0x18006dbf9  call    cs:__imp_NtQueryInformationToken
0x18006dc00  nop     dword ptr [rax+rax+00h]
0x18006dc05  mov     ecx, 80000000h
0x18006dc0a  mov     ebx, eax
0x18006dc0c  add     eax, ecx
0x18006dc0e  test    ecx, eax
0x18006dc10  jz      loc_18006DDE9
0x18006dc16  mov     ecx, [rsp+2A0h+TokenInformationLength]
0x18006dc1a  call    SafeAllocaAllocateFromHeap
0x18006dc1f  mov     rsi, rax
0x18006dc22  test    rax, rax
0x18006dc25  jz      loc_18006DDF7
0x18006dc2b  mov     r9d, [rsp+2A0h+TokenInformationLength]; TokenInformationLength
0x18006dc30  lea     rax, [rsp+2A0h+TokenInformationLength]
0x18006dc35  mov     r8, rsi; TokenInformation
0x18006dc38  mov     [rsp+2A0h+ReturnLength], rax; ReturnLength
0x18006dc3d  mov     edx, 1; TokenInformationClass
0x18006dc42  mov     rcx, rdi; TokenHandle
0x18006dc45  call    cs:__imp_NtQueryInformationToken
0x18006dc4c  nop     dword ptr [rax+rax+00h]
0x18006dc51  mov     ebx, eax
0x18006dc53  test    eax, eax
0x18006dc55  js      loc_18006DDB3
0x18006dc5b  mov     rbx, [rsi]
0x18006dc5e  lea     rcx, [rbp+1A0h+SourceSid]; void *
0x18006dc65  xor     edx, edx; Val
0x18006dc67  lea     r8d, [rdx+44h]; Size
0x18006dc6b  call    memset_0
0x18006dc70  mov     rcx, rbx; Sid
0x18006dc73  call    cs:__imp_RtlLengthSid
0x18006dc7a  nop     dword ptr [rax+rax+00h]
0x18006dc7f  mov     r8d, eax; Size
0x18006dc82  mov     rdx, rbx; Src
0x18006dc85  lea     rcx, [rbp+1A0h+SourceSid]; void *
0x18006dc8c  call    memcpy_0
0x18006dc91  mov     r9d, 4; TokenInformationLength
0x18006dc97  lea     rax, [rsp+2A0h+TokenInformationLength]
0x18006dc9c  lea     r8, [rbp+1A0h+TokenInformation]; TokenInformation
0x18006dca3  mov     [rsp+2A0h+ReturnLength], rax; ReturnLength
0x18006dca8  mov     rcx, rdi; TokenHandle
0x18006dcab  lea     edx, [r9+8]; TokenInformationClass
0x18006dcaf  call    cs:__imp_NtQueryInformationToken
0x18006dcb6  nop     dword ptr [rax+rax+00h]
0x18006dcbb  mov     ebx, eax
0x18006dcbd  test    eax, eax
0x18006dcbf  js      loc_18006DDB3
0x18006dcc5  lea     rdx, [rsp+2A0h+var_26C]
0x18006dcca  mov     rcx, rdi
0x18006dccd  call    cs:__imp_PsmQueryBackgroundActivationType
0x18006dcd4  nop     dword ptr [rax+rax+00h]
0x18006dcd9  mov     ebx, eax
0x18006dcdb  test    eax, eax
0x18006dcdd  js      loc_18006DDB3
0x18006dce3  mov     ecx, [rsp+2A0h+var_26C]
0x18006dce7  lea     rdx, [rbp+1A0h+var_40]
0x18006dcee  mov     eax, 1
0x18006dcf3  shl     eax, cl
0x18006dcf5  mov     rcx, rdi
0x18006dcf8  mov     [rbp+1A0h+var_48], eax
0x18006dcfe  call    cs:__imp_RtlQueryTokenHostIdAsUlong64
0x18006dd05  nop     dword ptr [rax+rax+00h]
0x18006dd0a  mov     ebx, eax
0x18006dd0c  test    eax, eax
0x18006dd0e  js      loc_18006DDB3
0x18006dd14  mov     rbx, [rbp+1A0h+var_40]
0x18006dd1b  xor     edx, edx; Val
0x18006dd1d  mov     edi, [rbp+1A0h+var_48]
0x18006dd23  mov     r8d, 228h; Size
0x18006dd29  mov     r15d, [rbp+1A0h+TokenInformation]
0x18006dd30  mov     rcx, r14; void *
0x18006dd33  call    memset_0
0x18006dd38  mov     edx, 7FFFFFFEh
0x18006dd3d  lea     r9, [rsp+2A0h+var_260]
0x18006dd42  mov     r8d, 0E8h
0x18006dd48  mov     rax, r14
0x18006dd4b  test    rdx, rdx
0x18006dd4e  jz      short loc_18006DD6D
0x18006dd50  movzx   ecx, word ptr [r9]
0x18006dd54  test    cx, cx
0x18006dd57  jz      short loc_18006DD6D
0x18006dd59  mov     [rax], cx
0x18006dd5c  add     r9, 2
0x18006dd60  add     rax, 2
0x18006dd64  dec     rdx
0x18006dd67  sub     r8, 1
0x18006dd6b  jnz     short loc_18006DD4B
0x18006dd6d  test    r8, r8
0x18006dd70  lea     rdx, [rax-2]
0x18006dd74  lea     r8, [rbp+1A0h+SourceSid]; SourceSid
0x18006dd7b  mov     ecx, 44h ; 'D'; DestinationSidLength
0x18006dd80  cmovnz  rdx, rax
0x18006dd84  mov     [rdx], r12w
0x18006dd88  lea     rdx, [r14+1D0h]; DestinationSid
0x18006dd8f  call    cs:__imp_RtlCopySid
0x18006dd96  nop     dword ptr [rax+rax+00h]
0x18006dd9b  mov     [r14+220h], rbx
0x18006dda2  mov     ebx, r12d
0x18006dda5  mov     [r14+214h], r15d
0x18006ddac  mov     [r14+218h], edi
0x18006ddb3  mov     rcx, rsi
0x18006ddb6  call    CempHeapFree
0x18006ddbb  mov     eax, ebx
0x18006ddbd  mov     rcx, [rbp+1A0h+var_30]
0x18006ddc4  xor     rcx, rsp; StackCookie
0x18006ddc7  call    __security_check_cookie
0x18006ddcc  lea     r11, [rsp+2A0h+var_20]
0x18006ddd4  mov     rbx, [r11+40h]
0x18006ddd8  mov     rsi, [r11+48h]
0x18006dddc  mov     rsp, r11
0x18006dddf  pop     r15
0x18006dde1  pop     r14
0x18006dde3  pop     r12
0x18006dde5  pop     rdi
0x18006dde6  pop     rbp
0x18006dde7  retn
0x18006dde9  cmp     ebx, 0C0000023h
0x18006ddef  jz      loc_18006DC16
0x18006ddf5  jmp     short loc_18006DDBB
0x18006ddf7  mov     ebx, 0C0000017h
0x18006ddfc  jmp     short loc_18006DDBB
```
