# CCredentialGroup::InitializeClientNameInfo(void *)

- ea: `0x180022840`
- end: `0x180022a8d`
- name: `?InitializeClientNameInfo@CCredentialGroup@@AEAAKPEAX@Z`
- size: `589`
- prototype: `unsigned int __fastcall(CCredentialGroup *__hidden this, void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800112c0`

## callees

- `0x180021da8`
- `0x180021eb0`
- `0x180022840`
- `0x1800597b0`
- `0x18005a160`
- `0x180088a54`
- `0x180091010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180022908`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180022908`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022a1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022a44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022a1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022a44`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800229fb`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800229fb`
- `ntdll!NtSetInformationThread` at `0x1800228c0`
- `ntdll!NtSetInformationThread` at `0x1800228c0`
- `ntdll!RtlNtStatusToDosError` at `0x1800228d1`
- `ntdll!RtlNtStatusToDosError` at `0x1800228d1`
- `SspiCli!GetUserNameExW` at `0x1800228f0`
- `SspiCli!GetUserNameExW` at `0x1800228f0`

## pseudocode

```c
__int64 __fastcall CCredentialGroup::InitializeClientNameInfo(CCredentialGroup *this, void *a2)
{
  __int64 v4; // rdx
  __int64 v5; // rcx
  int v6; // ebp
  int v7; // eax
  ULONG v8; // esi
  wchar_t *v9; // rax
  wchar_t *v10; // rbx
  __int64 v11; // rdi
  __int64 v12; // rax
  unsigned int v13; // r14d
  void *v14; // rax
  void *v15; // rax
  DWORD LastError; // eax
  ULONG nSize; // [rsp+20h] [rbp-458h] BYREF
  void *ThreadInformation; // [rsp+28h] [rbp-450h] BYREF
  WCHAR NameBuffer[520]; // [rsp+30h] [rbp-448h] BYREF

  memset_0(NameBuffer, 0, 0x404u);
  v6 = 0;
  nSize = 514;
  ThreadInformation = a2;
  if ( !LsaTable )
  {
    v8 = 0;
LABEL_7:
    if ( GetUserNameExW(NameDnsDomain, NameBuffer, &nSize) )
    {
      v9 = wcsrchr(NameBuffer, 0x5Cu);
      v10 = v9;
      if ( v9 )
      {
        v11 = -1;
        *v9 = 0;
        v12 = -1;
        do
          ++v12;
        while ( v10[v12 + 1] );
        v13 = (unsigned __int16)v12 + 1;
        v14 = SPExternalAlloc(2 * v13);
        *((_QWORD *)this + 118) = v14;
        if ( v14 )
        {
          memcpy_0(v14, v10 + 1, 2LL * v13);
          do
            ++v11;
          while ( NameBuffer[v11] );
          nSize = (unsigned __int16)v11 + 1;
          v15 = SPExternalAlloc(2 * nSize);
          *((_QWORD *)this + 119) = v15;
          if ( v15 )
            memcpy_0(v15, NameBuffer, 2LL * nSize);
          else
            v8 = 14;
        }
        else
        {
          v8 = 14;
        }
      }
      else
      {
        v8 = 1359;
      }
    }
    else if ( GetLastError() != 1332
           && WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_4353d526375b3dcf7f004b46f692ad9d_Traceguids, LastError);
    }
    goto LABEL_16;
  }
  if ( a2 )
    v7 = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &ThreadInformation, 8u);
  else
    v7 = (*(__int64 (__fastcall **)(__int64, __int64))(LsaTable + 88))(v5, v4);
  if ( v7 >= 0 )
    v6 = 1;
  v8 = RtlNtStatusToDosError(v7);
  if ( !v8 )
    goto LABEL_7;
LABEL_16:
  if ( v6 )
    RevertToSelf();
  return v8;
}

```

## disassembly

```asm
0x180022840  mov     r11, rsp
0x180022843  push    rsi
0x180022844  sub     rsp, 470h
0x18002284b  mov     rax, cs:__security_cookie
0x180022852  xor     rax, rsp
0x180022855  mov     [rsp+478h+var_38], rax
0x18002285d  mov     [r11+18h], rbx
0x180022861  mov     r8d, 404h; Size
0x180022867  mov     [r11-10h], rbp
0x18002286b  mov     rbx, rdx
0x18002286e  mov     [r11-28h], r15
0x180022872  xor     edx, edx; Val
0x180022874  mov     r15, rcx
0x180022877  lea     rcx, [rsp+478h+NameBuffer]; void *
0x18002287c  call    memset_0
0x180022881  mov     rax, cs:LsaTable
0x180022888  xor     ebp, ebp
0x18002288a  mov     [rsp+478h+nSize], 202h
0x180022892  mov     [rsp+478h+ThreadInformation], rbx
0x180022897  test    rax, rax
0x18002289a  jz      loc_180022A6E
0x1800228a0  test    rbx, rbx
0x1800228a3  jz      loc_180022A75
0x1800228a9  mov     r9d, 8; ThreadInformationLength
0x1800228af  lea     r8, [rsp+478h+ThreadInformation]; ThreadInformation
0x1800228b4  mov     edx, 5; ThreadInformationClass
0x1800228b9  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x1800228c0  call    cs:__imp_NtSetInformationThread
0x1800228c6  test    eax, eax
0x1800228c8  js      short loc_1800228CF
0x1800228ca  mov     ebp, 1
0x1800228cf  mov     ecx, eax; Status
0x1800228d1  call    cs:__imp_RtlNtStatusToDosError
0x1800228d7  mov     esi, eax
0x1800228d9  test    eax, eax
0x1800228db  jnz     loc_1800229BD
0x1800228e1  lea     r8, [rsp+478h+nSize]; nSize
0x1800228e6  mov     ecx, 0Ch; NameFormat
0x1800228eb  lea     rdx, [rsp+478h+NameBuffer]; lpNameBuffer
0x1800228f0  call    cs:__imp_GetUserNameExW
0x1800228f6  test    al, al
0x1800228f8  jz      loc_180022A1A
0x1800228fe  mov     edx, 5Ch ; '\'; Ch
0x180022903  lea     rcx, [rsp+478h+NameBuffer]; Str
0x180022908  call    cs:__imp_wcsrchr
0x18002290e  mov     rbx, rax
0x180022911  test    rax, rax
0x180022914  jz      loc_180022A83
0x18002291a  mov     [rsp+478h+var_18], rdi
0x180022922  xor     eax, eax
0x180022924  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x18002292b  mov     [rbx], ax
0x18002292e  mov     rax, rdi
0x180022931  mov     [rsp+478h+var_20], r14
0x180022939  nop     dword ptr [rax+00000000h]
0x180022940  inc     rax
0x180022943  cmp     word ptr [rbx+rax*2+2], 0
0x180022949  jnz     short loc_180022940
0x18002294b  movzx   r14d, ax
0x18002294f  inc     r14d
0x180022952  lea     ecx, [r14+r14]; uBytes
0x180022956  call    ?SPExternalAlloc@@YAPEAXK@Z; SPExternalAlloc(ulong)
0x18002295b  mov     [r15+3B0h], rax
0x180022962  test    rax, rax
0x180022965  jz      loc_1800229F4
0x18002296b  mov     r8d, r14d
0x18002296e  lea     rdx, [rbx+2]; Src
0x180022972  add     r8, r8; Size
0x180022975  mov     rcx, rax; void *
0x180022978  call    memcpy_0
0x18002297d  lea     rax, [rsp+478h+NameBuffer]
0x180022982  inc     rdi
0x180022985  cmp     word ptr [rax+rdi*2], 0
0x18002298a  jnz     short loc_180022982
0x18002298c  movzx   ecx, di
0x18002298f  inc     ecx
0x180022991  mov     [rsp+478h+nSize], ecx
0x180022995  add     ecx, ecx; uBytes
0x180022997  call    ?SPExternalAlloc@@YAPEAXK@Z; SPExternalAlloc(ulong)
0x18002299c  mov     [r15+3B8h], rax
0x1800229a3  test    rax, rax
0x1800229a6  jnz     short loc_180022A03
0x1800229a8  mov     esi, 0Eh
0x1800229ad  mov     rdi, [rsp+478h+var_18]
0x1800229b5  mov     r14, [rsp+478h+var_20]
0x1800229bd  mov     r15, [rsp+478h+var_28]
0x1800229c5  test    ebp, ebp
0x1800229c7  mov     rbp, [rsp+478h+var_10]
0x1800229cf  mov     rbx, [rsp+478h+arg_10]
0x1800229d7  jnz     short loc_1800229FB
0x1800229d9  mov     eax, esi
0x1800229db  mov     rcx, [rsp+478h+var_38]
0x1800229e3  xor     rcx, rsp; StackCookie
0x1800229e6  call    __security_check_cookie
0x1800229eb  add     rsp, 470h
0x1800229f2  pop     rsi
0x1800229f3  retn
0x1800229f4  mov     esi, 0Eh
0x1800229f9  jmp     short loc_1800229AD
0x1800229fb  call    cs:__imp_RevertToSelf
0x180022a01  jmp     short loc_1800229D9
0x180022a03  mov     r8d, [rsp+478h+nSize]
0x180022a08  lea     rdx, [rsp+478h+NameBuffer]; Src
0x180022a0d  add     r8, r8; Size
0x180022a10  mov     rcx, rax; void *
0x180022a13  call    memcpy_0
0x180022a18  jmp     short loc_1800229AD
0x180022a1a  call    cs:__imp_GetLastError
0x180022a20  cmp     eax, 534h
0x180022a25  jz      short loc_1800229BD
0x180022a27  mov     rax, cs:WPP_GLOBAL_Control
0x180022a2e  lea     rcx, WPP_GLOBAL_Control
0x180022a35  cmp     rax, rcx
0x180022a38  jz      short loc_1800229BD
0x180022a3a  test    byte ptr [rax+1Ch], 2
0x180022a3e  jz      loc_1800229BD
0x180022a44  call    cs:__imp_GetLastError
0x180022a4a  mov     rcx, cs:WPP_GLOBAL_Control
0x180022a51  lea     r8, WPP_4353d526375b3dcf7f004b46f692ad9d_Traceguids
0x180022a58  mov     edx, 0Ah
0x180022a5d  mov     r9d, eax
0x180022a60  mov     rcx, [rcx+10h]
0x180022a64  call    WPP_SF_d
0x180022a69  jmp     loc_1800229BD
0x180022a6e  xor     esi, esi
0x180022a70  jmp     loc_1800228E1
0x180022a75  mov     rax, [rax+58h]
0x180022a79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022a7e  jmp     loc_1800228C6
0x180022a83  mov     esi, 54Fh
0x180022a88  jmp     loc_1800229BD
```
