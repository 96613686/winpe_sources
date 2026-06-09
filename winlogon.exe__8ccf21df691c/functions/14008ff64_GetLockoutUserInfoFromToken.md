# GetLockoutUserInfoFromToken

- ea: `0x14008ff64`
- end: `0x1400901c0`
- name: `GetLockoutUserInfoFromToken`
- size: `604`
- prototype: `__int64 __usercall@<rax>(HANDLE hExistingToken@<rcx>, void *)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14008efdc`
- `0x14008fd2c`

## callees

- `0x1400057f4`
- `0x14008f7e8`
- `0x14008ff64`
- `0x14009040c`
- `0x140090530`
- `0x14009cc54`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140090051`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140090051`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140090040`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140090040`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14008ffb1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14009009c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14008ffb1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14009009c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14008ffa7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140090092`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14008ffa7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140090092`
- `ntdll!RtlLengthSid` at `0x1400900f4`
- `ntdll!RtlLengthSid` at `0x1400900f4`
- `ntdll!RtlNtStatusToDosError` at `0x140090168`
- `ntdll!RtlNtStatusToDosError` at `0x140090168`

## pseudocode

```c
__int64 __fastcall GetLockoutUserInfoFromToken(HANDLE hExistingToken, int a2, _DWORD *a3, __int64 a4, void *a5)
{
  DWORD v8; // ebx
  __int64 v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // r9
  CUser *v12; // rax
  __int64 v13; // rdx
  SIZE_T v14; // rbx
  HANDLE ProcessHeap; // rax
  PSID *v16; // rbx
  DWORD LastError; // eax
  CUser *v18; // r10
  ULONG v19; // eax
  NTSTATUS v20; // eax
  PSID *v22; // [rsp+60h] [rbp+18h] BYREF
  SIZE_T dwBytes; // [rsp+68h] [rbp+20h] BYREF

  v22 = 0;
  LODWORD(dwBytes) = 0;
  *a3 = 0;
  if ( GetTokenInformation(hExistingToken, TokenUser, 0, 0, (PDWORD)&dwBytes) || (v8 = GetLastError(), v8 == 122) )
  {
    if ( !(_DWORD)dwBytes )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_27;
      }
      v13 = 41;
LABEL_26:
      WPP_SF_d(*((_QWORD *)v12 + 2), v13, WPP_8d12472ee3e0397472f1167aeb1d1409_Traceguids, 87);
LABEL_27:
      v8 = 87;
      goto LABEL_36;
    }
    v14 = (unsigned int)dwBytes;
    ProcessHeap = GetProcessHeap();
    v16 = (PSID *)HeapAlloc(ProcessHeap, 8u, v14);
    CAutoPtr<unsigned short *,&void FreeHeap<unsigned short *>(unsigned short *)>::Free(&v22);
    v22 = v16;
    if ( !v16 )
    {
      v8 = 14;
      goto LABEL_36;
    }
    if ( !GetTokenInformation(hExistingToken, TokenUser, v16, dwBytes, (PDWORD)&dwBytes) )
    {
      LastError = GetLastError();
      v8 = LastError;
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_36;
      }
      v10 = 42;
      goto LABEL_19;
    }
    v19 = RtlLengthSid(*v16);
    if ( v19 > 0x44 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_27;
      }
      v13 = 43;
      goto LABEL_26;
    }
    memcpy_0(a5, *v16, v19);
    if ( a2 )
    {
      v20 = IsUserAdminFromLUAToken(hExistingToken);
      if ( v20 < 0 )
      {
        LastError = RtlNtStatusToDosError(v20);
        v8 = LastError;
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_36;
        }
        v10 = 44;
LABEL_19:
        v9 = *((_QWORD *)v18 + 2);
        v11 = LastError;
        goto LABEL_20;
      }
    }
    else
    {
      *a3 = IsUserAdminFromS4UToken(hExistingToken);
    }
    v8 = 0;
    goto LABEL_36;
  }
  if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v9 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    v10 = 40;
    v11 = v8;
LABEL_20:
    WPP_SF_d(v9, v10, WPP_8d12472ee3e0397472f1167aeb1d1409_Traceguids, v11);
  }
LABEL_36:
  CAutoPtr<unsigned short *,&void FreeHeap<unsigned short *>(unsigned short *)>::Free(&v22);
  return v8;
}

```

## disassembly

```asm
0x14008ff64  mov     rax, rsp
0x14008ff67  mov     [rax+8], rbx
0x14008ff6b  mov     [rax+20h], r9d
0x14008ff6f  push    rbp
0x14008ff70  push    rsi
0x14008ff71  push    rdi
0x14008ff72  sub     rsp, 30h
0x14008ff76  xor     r9d, r9d; TokenInformationLength
0x14008ff79  mov     qword ptr [rax+18h], 0
0x14008ff81  mov     dword ptr [rax+20h], 0
0x14008ff88  lea     rax, [rax+20h]
0x14008ff8c  mov     rsi, r8
0x14008ff8f  mov     dword ptr [r8], 0
0x14008ff96  mov     ebp, edx
0x14008ff98  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x14008ff9d  lea     edx, [r9+1]; TokenInformationClass
0x14008ffa1  xor     r8d, r8d; TokenInformation
0x14008ffa4  mov     rdi, rcx
0x14008ffa7  call    cs:__imp_GetTokenInformation
0x14008ffad  test    eax, eax
0x14008ffaf  jnz     short loc_14008FFFD
0x14008ffb1  call    cs:__imp_GetLastError
0x14008ffb7  mov     ebx, eax
0x14008ffb9  cmp     eax, 7Ah ; 'z'
0x14008ffbc  jz      short loc_14008FFFD
0x14008ffbe  mov     rax, cs:WPP_GLOBAL_Control
0x14008ffc5  lea     rcx, WPP_GLOBAL_Control
0x14008ffcc  cmp     rax, rcx
0x14008ffcf  jz      loc_1400901A7
0x14008ffd5  test    dword ptr [rax+1Ch], 1000h
0x14008ffdc  jz      loc_1400901A7
0x14008ffe2  cmp     byte ptr [rax+19h], 2
0x14008ffe6  jb      loc_1400901A7
0x14008ffec  mov     rcx, [rax+10h]
0x14008fff0  mov     edx, 28h ; '('
0x14008fff5  mov     r9d, ebx
0x14008fff8  jmp     loc_1400900E0
0x14008fffd  mov     eax, dword ptr [rsp+48h+dwBytes]
0x140090001  test    eax, eax
0x140090003  jnz     short loc_14009003D
0x140090005  mov     rax, cs:WPP_GLOBAL_Control
0x14009000c  lea     rcx, WPP_GLOBAL_Control
0x140090013  cmp     rax, rcx
0x140090016  jz      loc_14009013C
0x14009001c  test    dword ptr [rax+1Ch], 1000h
0x140090023  jz      loc_14009013C
0x140090029  cmp     byte ptr [rax+19h], 2
0x14009002d  jb      loc_14009013C
0x140090033  mov     edx, 29h ; ')'
0x140090038  jmp     loc_140090126
0x14009003d  mov     rbx, rax
0x140090040  call    cs:__imp_GetProcessHeap
0x140090046  mov     r8, rbx; dwBytes
0x140090049  mov     edx, 8; dwFlags
0x14009004e  mov     rcx, rax; hHeap
0x140090051  call    cs:__imp_HeapAlloc
0x140090057  lea     rcx, [rsp+48h+arg_10]
0x14009005c  mov     rbx, rax
0x14009005f  call    ?Free@?$CAutoPtr@PEAG$1??$FreeHeap@PEAG@@YAXPEAG@Z@@AEAAXXZ; CAutoPtr<ushort *,&FreeHeap<ushort *>(ushort *)>::Free(void)
0x140090064  mov     [rsp+48h+arg_10], rbx
0x140090069  test    rbx, rbx
0x14009006c  jnz     short loc_140090078
0x14009006e  mov     ebx, 0Eh
0x140090073  jmp     loc_1400901A7
0x140090078  mov     r9d, dword ptr [rsp+48h+dwBytes]; TokenInformationLength
0x14009007d  lea     rax, [rsp+48h+dwBytes]
0x140090082  mov     r8, rbx; TokenInformation
0x140090085  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x14009008a  mov     edx, 1; TokenInformationClass
0x14009008f  mov     rcx, rdi; TokenHandle
0x140090092  call    cs:__imp_GetTokenInformation
0x140090098  test    eax, eax
0x14009009a  jnz     short loc_1400900F1
0x14009009c  call    cs:__imp_GetLastError
0x1400900a2  mov     ebx, eax
0x1400900a4  mov     r10, cs:WPP_GLOBAL_Control
0x1400900ab  lea     rcx, WPP_GLOBAL_Control
0x1400900b2  cmp     r10, rcx
0x1400900b5  jz      loc_1400901A7
0x1400900bb  test    dword ptr [r10+1Ch], 1000h
0x1400900c3  jz      loc_1400901A7
0x1400900c9  cmp     byte ptr [r10+19h], 2
0x1400900ce  jb      loc_1400901A7
0x1400900d4  mov     edx, 2Ah ; '*'
0x1400900d9  mov     rcx, [r10+10h]
0x1400900dd  mov     r9d, eax
0x1400900e0  lea     r8, WPP_8d12472ee3e0397472f1167aeb1d1409_Traceguids
0x1400900e7  call    WPP_SF_d
0x1400900ec  jmp     loc_1400901A7
0x1400900f1  mov     rcx, [rbx]; Sid
0x1400900f4  call    cs:__imp_RtlLengthSid
0x1400900fa  cmp     eax, 44h ; 'D'
0x1400900fd  jbe     short loc_140090143
0x1400900ff  mov     rax, cs:WPP_GLOBAL_Control
0x140090106  lea     rcx, WPP_GLOBAL_Control
0x14009010d  cmp     rax, rcx
0x140090110  jz      short loc_14009013C
0x140090112  test    dword ptr [rax+1Ch], 1000h
0x140090119  jz      short loc_14009013C
0x14009011b  cmp     byte ptr [rax+19h], 2
0x14009011f  jb      short loc_14009013C
0x140090121  mov     edx, 2Bh ; '+'
0x140090126  mov     rcx, [rax+10h]
0x14009012a  lea     r8, WPP_8d12472ee3e0397472f1167aeb1d1409_Traceguids
0x140090131  mov     r9d, 57h ; 'W'
0x140090137  call    WPP_SF_d
0x14009013c  mov     ebx, 57h ; 'W'
0x140090141  jmp     short loc_1400901A7
0x140090143  mov     rdx, [rbx]; Src
0x140090146  mov     rcx, [rsp+48h+arg_20]; void *
0x14009014b  mov     r8d, eax; Size
0x14009014e  call    memcpy_0
0x140090153  mov     rcx, rdi; TokenHandle
0x140090156  test    ebp, ebp
0x140090158  jz      short loc_14009019E
0x14009015a  mov     rdx, rsi
0x14009015d  call    IsUserAdminFromLUAToken
0x140090162  test    eax, eax
0x140090164  jns     short loc_1400901A5
0x140090166  mov     ecx, eax; Status
0x140090168  call    cs:__imp_RtlNtStatusToDosError
0x14009016e  mov     ebx, eax
0x140090170  mov     r10, cs:WPP_GLOBAL_Control
0x140090177  lea     rcx, WPP_GLOBAL_Control
0x14009017e  cmp     r10, rcx
0x140090181  jz      short loc_1400901A7
0x140090183  test    dword ptr [r10+1Ch], 1000h
0x14009018b  jz      short loc_1400901A7
0x14009018d  cmp     byte ptr [r10+19h], 2
0x140090192  jb      short loc_1400901A7
0x140090194  mov     edx, 2Ch ; ','
0x140090199  jmp     loc_1400900D9
0x14009019e  call    IsUserAdminFromS4UToken
0x1400901a3  mov     [rsi], eax
0x1400901a5  xor     ebx, ebx
0x1400901a7  lea     rcx, [rsp+48h+arg_10]
0x1400901ac  call    ?Free@?$CAutoPtr@PEAG$1??$FreeHeap@PEAG@@YAXPEAG@Z@@AEAAXXZ; CAutoPtr<ushort *,&FreeHeap<ushort *>(ushort *)>::Free(void)
0x1400901b1  mov     eax, ebx
0x1400901b3  mov     rbx, [rsp+48h+arg_0]
0x1400901b8  add     rsp, 30h
0x1400901bc  pop     rdi
0x1400901bd  pop     rsi
0x1400901be  pop     rbp
0x1400901bf  retn
```
