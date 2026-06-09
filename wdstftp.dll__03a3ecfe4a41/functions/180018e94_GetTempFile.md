# GetTempFile

- ea: `0x180018e94`
- end: `0x180019089`
- name: `GetTempFile`
- size: `501`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x18000f124`
- `0x180019090`
- `0x18001b8c4`
- `0x18001bae8`

## callees

- `0x180010efc`
- `0x180011850`
- `0x180018e94`
- `0x1800607b0`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180018f91`
- `KERNEL32!HeapFree` at `0x180018f91`
- `KERNEL32!EnterCriticalSection` at `0x180018f1e`
- `KERNEL32!EnterCriticalSection` at `0x180018f1e`
- `KERNEL32!LeaveCriticalSection` at `0x180018fa1`
- `KERNEL32!LeaveCriticalSection` at `0x180018fa1`
- `KERNEL32!LeaveCriticalSection` at `0x180061b73`
- `KERNEL32!SetLastError` at `0x18001903b`
- `KERNEL32!SetLastError` at `0x180019051`
- `KERNEL32!SetLastError` at `0x18001903b`
- `KERNEL32!SetLastError` at `0x180019051`
- `KERNEL32!GetProcessHeap` at `0x180018f7d`
- `KERNEL32!GetProcessHeap` at `0x180018f7d`
- `RPCRT4!RpcStringFreeW` at `0x180019025`
- `RPCRT4!RpcStringFreeW` at `0x180019025`
- `RPCRT4!UuidToStringW` at `0x180018ffb`
- `RPCRT4!UuidToStringW` at `0x180018ffb`
- `RPCRT4!UuidCreate` at `0x180018fe1`
- `RPCRT4!UuidCreate` at `0x180018fe1`

## pseudocode

```c
__int64 __fastcall GetTempFile(__int64 a1)
{
  RPC_WSTR v2; // rdi
  int v3; // r15d
  int v4; // ecx
  __int64 v5; // rsi
  __int64 i; // rax
  unsigned __int16 *v7; // rsi
  __int64 v8; // r14
  RPC_WSTR *v9; // r14
  __int64 v10; // rax
  HANDLE ProcessHeap; // rax
  const WCHAR *WimTempPath; // rbx
  RPC_WSTR StringUuid[2]; // [rsp+20h] [rbp-48h] BYREF
  UUID Uuid; // [rsp+30h] [rbp-38h] BYREF

  v2 = 0;
  v3 = -1;
  if ( a1 && (v4 = *(_DWORD *)a1, (unsigned int)(*(_DWORD *)a1 + 17960959) <= 1) )
  {
    if ( v4 != -17960958 )
      goto LABEL_20;
    v5 = a1;
    for ( i = *(_QWORD *)(a1 + 64); i; i = *(_QWORD *)(i + 64) )
      v5 = i;
    v7 = (unsigned __int16 *)(v5 + 520);
    StringUuid[0] = v7;
    EnterCriticalSection((LPCRITICAL_SECTION)v7);
    v8 = a1;
    if ( *(_DWORD *)a1 == -17960958 )
    {
      while ( *(_QWORD *)(v8 + 64) )
        v8 = *(_QWORD *)(v8 + 64);
      v9 = *(RPC_WSTR **)(v8 + 232);
      if ( v9 )
      {
        v10 = a1;
        if ( a1 )
          v3 = *(_DWORD *)a1;
        if ( v3 == -17960958 )
        {
          while ( *(_QWORD *)(v10 + 64) )
            v10 = *(_QWORD *)(v10 + 64);
          *(_QWORD *)(v10 + 232) = v9[1];
        }
        v2 = *v9;
        StringUuid[1] = *v9;
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v9);
      }
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)v7);
    if ( !v2 )
    {
LABEL_20:
      WimTempPath = (const WCHAR *)GetWimTempPath(a1);
      if ( WimTempPath )
      {
        StringUuid[0] = 0;
        *(_QWORD *)&Uuid.Data1 = 0;
        *(_QWORD *)Uuid.Data4 = 0;
        if ( !UuidCreate(&Uuid) && !UuidToStringW(&Uuid, StringUuid) )
        {
          if ( StringUuid[0] )
          {
            v2 = (RPC_WSTR)AllocAddPath(WimTempPath, StringUuid[0]);
            RpcStringFreeW(StringUuid);
          }
        }
      }
      else
      {
        SetLastError(0x660u);
      }
    }
    return (__int64)v2;
  }
  else
  {
    SetLastError(6u);
    return -1;
  }
}

```

## disassembly

```asm
0x180018e94  mov     [rsp+arg_8], rbx
0x180018e99  mov     [rsp+arg_10], rsi
0x180018e9e  mov     [rsp+arg_18], rdi
0x180018ea3  push    r12
0x180018ea5  push    r14
0x180018ea7  push    r15
0x180018ea9  sub     rsp, 50h
0x180018ead  mov     rax, cs:__security_cookie
0x180018eb4  xor     rax, rsp
0x180018eb7  mov     [rsp+68h+var_28], rax
0x180018ebc  mov     rbx, rcx
0x180018ebf  xor     edi, edi
0x180018ec1  or      r15d, 0FFFFFFFFh
0x180018ec5  mov     ecx, r15d
0x180018ec8  test    rbx, rbx
0x180018ecb  jz      loc_18001904C
0x180018ed1  mov     ecx, [rbx]
0x180018ed3  lea     eax, [rcx+1120FFFh]
0x180018ed9  cmp     eax, 1
0x180018edc  ja      loc_18001904C
0x180018ee2  mov     r12d, 0FEEDF002h
0x180018ee8  cmp     ecx, r12d
0x180018eeb  jnz     loc_180018FBA
0x180018ef1  mov     rsi, rbx
0x180018ef4  cmp     ecx, r12d
0x180018ef7  jz      short loc_180018EFD
0x180018ef9  xor     esi, esi
0x180018efb  jmp     short loc_180018F16
0x180018efd  mov     rax, [rbx+40h]
0x180018f01  jmp     short loc_180018F0A
0x180018f03  mov     rsi, rax
0x180018f06  mov     rax, [rax+40h]
0x180018f0a  test    rax, rax
0x180018f0d  jnz     short loc_180018F03
0x180018f0f  add     rsi, 208h
0x180018f16  mov     [rsp+68h+StringUuid], rsi
0x180018f1b  mov     rcx, rsi; lpCriticalSection
0x180018f1e  call    cs:__imp_EnterCriticalSection
0x180018f25  nop     dword ptr [rax+rax+00h]
0x180018f2a  nop
0x180018f2b  mov     r14, rbx
0x180018f2e  cmp     [rbx], r12d
0x180018f31  jnz     short loc_180018F9E
0x180018f33  mov     rax, [r14+40h]
0x180018f37  test    rax, rax
0x180018f3a  jz      short loc_180018F41
0x180018f3c  mov     r14, rax
0x180018f3f  jmp     short loc_180018F33
0x180018f41  mov     r14, [r14+0E8h]
0x180018f48  test    r14, r14
0x180018f4b  jz      short loc_180018F9E
0x180018f4d  mov     rdx, [r14+8]
0x180018f51  mov     rax, rbx
0x180018f54  test    rbx, rbx
0x180018f57  cmovnz  r15d, [rbx]
0x180018f5b  cmp     r15d, r12d
0x180018f5e  jnz     short loc_180018F75
0x180018f60  mov     rcx, [rax+40h]
0x180018f64  test    rcx, rcx
0x180018f67  jz      short loc_180018F6E
0x180018f69  mov     rax, rcx
0x180018f6c  jmp     short loc_180018F60
0x180018f6e  mov     [rax+0E8h], rdx
0x180018f75  mov     rdi, [r14]
0x180018f78  mov     [rsp+68h+var_40], rdi
0x180018f7d  call    cs:__imp_GetProcessHeap
0x180018f84  nop     dword ptr [rax+rax+00h]
0x180018f89  mov     rcx, rax; hHeap
0x180018f8c  mov     r8, r14; lpMem
0x180018f8f  xor     edx, edx; dwFlags
0x180018f91  call    cs:__imp_HeapFree
0x180018f98  nop     dword ptr [rax+rax+00h]
0x180018f9d  nop
0x180018f9e  mov     rcx, rsi; lpCriticalSection
0x180018fa1  call    cs:__imp_LeaveCriticalSection
0x180018fa8  nop     dword ptr [rax+rax+00h]
0x180018fad  test    rdi, rdi
0x180018fb0  jz      short loc_180018FBA
0x180018fb2  mov     rax, rdi
0x180018fb5  jmp     loc_180019061
0x180018fba  mov     rcx, rbx
0x180018fbd  call    GetWimTempPath
0x180018fc2  mov     rbx, rax
0x180018fc5  test    rax, rax
0x180018fc8  jz      short loc_180019036
0x180018fca  and     [rsp+68h+StringUuid], 0
0x180018fd0  xor     eax, eax
0x180018fd2  mov     qword ptr [rsp+68h+Uuid.Data1], rax
0x180018fd7  mov     qword ptr [rsp+68h+Uuid.Data4], rax
0x180018fdc  lea     rcx, [rsp+68h+Uuid]; Uuid
0x180018fe1  call    cs:__imp_UuidCreate
0x180018fe8  nop     dword ptr [rax+rax+00h]
0x180018fed  test    eax, eax
0x180018fef  jnz     short loc_180018FB2
0x180018ff1  lea     rdx, [rsp+68h+StringUuid]; StringUuid
0x180018ff6  lea     rcx, [rsp+68h+Uuid]; Uuid
0x180018ffb  call    cs:__imp_UuidToStringW
0x180019002  nop     dword ptr [rax+rax+00h]
0x180019007  test    eax, eax
0x180019009  jnz     short loc_180018FB2
0x18001900b  mov     rdx, [rsp+68h+StringUuid]; STRSAFE_PCNZWCH
0x180019010  test    rdx, rdx
0x180019013  jz      short loc_180018FB2
0x180019015  mov     rcx, rbx; lpFileName
0x180019018  call    AllocAddPath
0x18001901d  mov     rdi, rax
0x180019020  lea     rcx, [rsp+68h+StringUuid]; String
0x180019025  call    cs:__imp_RpcStringFreeW
0x18001902c  nop     dword ptr [rax+rax+00h]
0x180019031  jmp     loc_180018FB2
0x180019036  mov     ecx, 660h; dwErrCode
0x18001903b  call    cs:__imp_SetLastError
0x180019042  nop     dword ptr [rax+rax+00h]
0x180019047  jmp     loc_180018FB2
0x18001904c  mov     ecx, 6; dwErrCode
0x180019051  call    cs:__imp_SetLastError
0x180019058  nop     dword ptr [rax+rax+00h]
0x18001905d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180019061  mov     rcx, [rsp+68h+var_28]
0x180019066  xor     rcx, rsp; StackCookie
0x180019069  call    __security_check_cookie
0x18001906e  lea     r11, [rsp+68h+var_18]
0x180019073  mov     rbx, [r11+28h]
0x180019077  mov     rsi, [r11+30h]
0x18001907b  mov     rdi, [r11+38h]
0x18001907f  mov     rsp, r11
0x180019082  pop     r15
0x180019084  pop     r14
0x180019086  pop     r12
0x180019088  retn
0x180061b61  push    rbp
0x180061b63  sub     rsp, 20h
0x180061b67  mov     rbp, rdx
0x180061b6a  mov     rcx, [rbp+20h]
0x180061b6e  add     rsp, 20h
0x180061b72  pop     rbp
0x180061b73  jmp     cs:__imp_LeaveCriticalSection
```
