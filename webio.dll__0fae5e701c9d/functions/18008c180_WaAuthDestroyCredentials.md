# WaAuthDestroyCredentials

- ea: `0x18008c180`
- end: `0x18008c248`
- name: `WaAuthDestroyCredentials`
- size: `200`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800046c4`
- `0x180004960`
- `0x180005168`
- `0x18003d1b0`
- `0x18006af94`
- `0x18006be4c`
- `0x18006cfdc`

## callees

- `0x180013820`
- `0x18008c180`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18008c18d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18008c18d`
- `SspiCli!SspiZeroAuthIdentity` at `0x18008c1a2`
- `SspiCli!SspiZeroAuthIdentity` at `0x18008c1a2`
- `SspiCli!DeleteSecurityContext` at `0x18008c220`
- `SspiCli!DeleteSecurityContext` at `0x18008c220`
- `SspiCli!FreeCredentialsHandle` at `0x18008c203`
- `SspiCli!FreeCredentialsHandle` at `0x18008c203`
- `SspiCli!SspiFreeAuthIdentity` at `0x18008c1b2`
- `SspiCli!SspiFreeAuthIdentity` at `0x18008c1b2`

## pseudocode

```c
__int64 __fastcall WaAuthDestroyCredentials(__int64 a1)
{
  void *v2; // rcx
  volatile signed __int32 *v3; // rcx
  _QWORD v5[3]; // [rsp+20h] [rbp-18h] BYREF

  DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 40));
  v2 = *(void **)(a1 + 80);
  if ( v2 )
  {
    SspiZeroAuthIdentity(v2);
    SspiFreeAuthIdentity(*(PSEC_WINNT_AUTH_IDENTITY_OPAQUE *)(a1 + 80));
    *(_QWORD *)(a1 + 80) = 0;
  }
  v3 = *(volatile signed __int32 **)(a1 + 16);
  if ( v3 )
  {
    if ( _InterlockedExchangeAdd(v3, 0xFFFFFFFF) == 1 )
    {
      v5[0] = v3;
      WxFreeHeapEx(v5);
    }
    *(_QWORD *)(a1 + 16) = 0;
  }
  if ( *(_QWORD *)(a1 + 24) != -1 && *(_QWORD *)(a1 + 32) != -1 )
    FreeCredentialsHandle((PCredHandle)(a1 + 24));
  if ( *(_QWORD *)(a1 + 88) != -1 && *(_QWORD *)(a1 + 96) != -1 )
    DeleteSecurityContext((PCtxtHandle)(a1 + 88));
  *(_DWORD *)a1 = 1684370019;
  v5[0] = a1;
  return WxFreeHeapEx(v5);
}

```

## disassembly

```asm
0x18008c180  push    rbx
0x18008c182  sub     rsp, 30h
0x18008c186  mov     rbx, rcx
0x18008c189  add     rcx, 28h ; '('; lpCriticalSection
0x18008c18d  call    cs:__imp_DeleteCriticalSection
0x18008c194  nop     dword ptr [rax+rax+00h]
0x18008c199  mov     rcx, [rbx+50h]; AuthData
0x18008c19d  test    rcx, rcx
0x18008c1a0  jz      short loc_18008C1C6
0x18008c1a2  call    cs:__imp_SspiZeroAuthIdentity
0x18008c1a9  nop     dword ptr [rax+rax+00h]
0x18008c1ae  mov     rcx, [rbx+50h]; AuthData
0x18008c1b2  call    cs:__imp_SspiFreeAuthIdentity
0x18008c1b9  nop     dword ptr [rax+rax+00h]
0x18008c1be  mov     qword ptr [rbx+50h], 0
0x18008c1c6  mov     rcx, [rbx+10h]
0x18008c1ca  test    rcx, rcx
0x18008c1cd  jz      short loc_18008C1F2
0x18008c1cf  or      eax, 0FFFFFFFFh
0x18008c1d2  lock xadd [rcx], eax
0x18008c1d6  cmp     eax, 1
0x18008c1d9  jnz     short loc_18008C1EA
0x18008c1db  mov     [rsp+38h+var_18], rcx
0x18008c1e0  lea     rcx, [rsp+38h+var_18]
0x18008c1e5  call    WxFreeHeapEx
0x18008c1ea  mov     qword ptr [rbx+10h], 0
0x18008c1f2  lea     rcx, [rbx+18h]; phCredential
0x18008c1f6  cmp     qword ptr [rcx], 0FFFFFFFFFFFFFFFFh
0x18008c1fa  jz      short loc_18008C20F
0x18008c1fc  cmp     qword ptr [rbx+20h], 0FFFFFFFFFFFFFFFFh
0x18008c201  jz      short loc_18008C20F
0x18008c203  call    cs:__imp_FreeCredentialsHandle
0x18008c20a  nop     dword ptr [rax+rax+00h]
0x18008c20f  lea     rcx, [rbx+58h]; phContext
0x18008c213  cmp     qword ptr [rcx], 0FFFFFFFFFFFFFFFFh
0x18008c217  jz      short loc_18008C22C
0x18008c219  cmp     qword ptr [rbx+60h], 0FFFFFFFFFFFFFFFFh
0x18008c21e  jz      short loc_18008C22C
0x18008c220  call    cs:__imp_DeleteSecurityContext
0x18008c227  nop     dword ptr [rax+rax+00h]
0x18008c22c  lea     rcx, [rsp+38h+var_18]
0x18008c231  mov     dword ptr [rbx], 64657263h
0x18008c237  mov     [rsp+38h+var_18], rbx
0x18008c23c  call    WxFreeHeapEx
0x18008c241  add     rsp, 30h
0x18008c245  pop     rbx
0x18008c246  retn
```
