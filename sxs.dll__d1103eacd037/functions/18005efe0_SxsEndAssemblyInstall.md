# SxsEndAssemblyInstall

- ea: `0x18005efe0`
- end: `0x18005f1dc`
- name: `SxsEndAssemblyInstall`
- size: `508`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000df40`
- `0x18001c270`
- `0x18002e98c`
- `0x18002fffc`
- `0x18005c978`
- `0x18005d2b0`
- `0x18005efe0`
- `0x18006a110`
- `0x18006b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f07f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f181`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f07f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f181`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005f069`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005f111`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005f1a0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005f069`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005f111`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005f1a0`

## pseudocode

```c
__int64 __fastcall SxsEndAssemblyInstall(__int64 a1, unsigned int a2, _DWORD *a3)
{
  const char *v6; // rcx
  DWORD LastError; // ebx
  int v8; // edx
  unsigned int v9; // r14d
  int v10; // eax
  int v11; // ebx
  unsigned int v12; // ebx
  int v14; // [rsp+20h] [rbp-40h] BYREF
  int v15; // [rsp+24h] [rbp-3Ch] BYREF
  int v16; // [rsp+28h] [rbp-38h] BYREF
  __int64 v17; // [rsp+30h] [rbp-30h]
  __int64 *v18; // [rsp+38h] [rbp-28h]
  __int64 v19; // [rsp+40h] [rbp-20h]
  int v20; // [rsp+48h] [rbp-18h]
  int *v21; // [rsp+50h] [rbp-10h]

  v14 = 0;
  v18 = &qword_1800747F0;
  v16 = 1;
  v21 = &v14;
  v17 = 0;
  v19 = 544438355;
  v20 = 386;
  CFrame::BaseEnter((CFrame *)&v16);
  v15 = 0;
  if ( !a1 )
  {
    v20 = 392;
LABEL_3:
    FusionpTraceParameterCheck(v6);
    SetLastError(0x57u);
    *v21 = 0;
    LastError = GetLastError();
    goto LABEL_24;
  }
  if ( (a2 & 0xF0FFFFFF) != 0 )
  {
    v20 = 398;
    goto LABEL_3;
  }
  if ( (((a2 & 0x3000000) - 0x1000000) & 0xFEFFFFFF) != 0 )
  {
    v20 = 403;
    goto LABEL_3;
  }
  if ( (a2 & 0x8000000) != 0 && a3 )
  {
    v20 = 412;
    goto LABEL_3;
  }
  v8 = (a2 >> 12) & 0x1000 | 8;
  if ( (a2 & 0x2000000) == 0 )
    v8 = (a2 >> 12) & 0x1000;
  v9 = v8 | 2;
  if ( (a2 & 0x4000000) == 0 )
    v9 = v8;
  if ( (a2 & 0x8000000) != 0 && a3 )
    *a3 = 1;
  SetLastError(0);
  v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, int *))(*(_QWORD *)a1 + 40LL))(a1, v9, &v15);
  v11 = v10;
  if ( v10 >= 0 )
  {
    if ( v15 == 2 )
    {
      CFnTracerWin32::MarkCOMFailure((CFnTracerWin32 *)&v16, -2147021886);
      FusionpTraceCOMFailureOrigination((const struct _CALL_SITE_INFO *)off_1800747D0, 0x80070BC2);
    }
    else
    {
      v14 = 1;
    }
  }
  else
  {
    FusionpTraceCOMFailure(v10, byte_18008517D);
    CFnTracerWin32::MarkCOMFailure((CFnTracerWin32 *)&v16, v11);
  }
  LastError = GetLastError();
  (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 16LL))(a1);
LABEL_24:
  SetLastError(LastError);
  v12 = v14;
  CFnTracerWin32::~CFnTracerWin32((CFnTracerWin32 *)&v16);
  return v12;
}

```

## disassembly

```asm
0x18005efe0  mov     [rsp-18h+arg_8], rbx
0x18005efe5  mov     [rsp-18h+arg_18], rsi
0x18005efea  push    rbp
0x18005efeb  push    rdi
0x18005efec  push    r14
0x18005efee  mov     rbp, rsp
0x18005eff1  sub     rsp, 60h
0x18005eff5  mov     rax, cs:__security_cookie
0x18005effc  xor     rax, rsp
0x18005efff  mov     [rbp+var_8], rax
0x18005f003  lea     rax, qword_1800747F0
0x18005f00a  mov     [rbp+var_40], 0
0x18005f011  mov     [rbp+var_28], rax
0x18005f015  mov     rdi, rcx
0x18005f018  lea     rax, [rbp+var_40]
0x18005f01c  mov     [rbp+var_38], 1
0x18005f023  lea     rcx, [rbp+var_38]; this
0x18005f027  mov     [rbp+var_10], rax
0x18005f02b  mov     rsi, r8
0x18005f02e  mov     [rbp+var_30], 0
0x18005f036  mov     ebx, edx
0x18005f038  mov     [rbp+var_20], 20737853h
0x18005f040  mov     [rbp+var_18], 182h
0x18005f047  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x18005f04c  mov     [rbp+var_3C], 0
0x18005f053  test    rdi, rdi
0x18005f056  jnz     short loc_18005F092
0x18005f058  mov     [rbp+var_18], 188h
0x18005f05f  call    ?FusionpTraceParameterCheck@@YAXPEBD@Z; FusionpTraceParameterCheck(char const *)
0x18005f064  mov     ecx, 57h ; 'W'; dwErrCode
0x18005f069  call    cs:__imp_SetLastError
0x18005f070  nop     dword ptr [rax+rax+00h]
0x18005f075  mov     rax, [rbp+var_10]
0x18005f079  mov     dword ptr [rax], 0
0x18005f07f  call    cs:__imp_GetLastError
0x18005f086  nop     dword ptr [rax+rax+00h]
0x18005f08b  mov     ebx, eax
0x18005f08d  jmp     loc_18005F19E
0x18005f092  test    ebx, 0F0FFFFFFh
0x18005f098  jz      short loc_18005F0A3
0x18005f09a  mov     [rbp+var_18], 18Eh
0x18005f0a1  jmp     short loc_18005F05F
0x18005f0a3  mov     eax, ebx
0x18005f0a5  and     eax, 3000000h
0x18005f0aa  sub     eax, 1000000h
0x18005f0af  test    eax, 0FEFFFFFFh
0x18005f0b4  jz      short loc_18005F0BF
0x18005f0b6  mov     [rbp+var_18], 193h
0x18005f0bd  jmp     short loc_18005F05F
0x18005f0bf  mov     r8d, ebx
0x18005f0c2  and     r8d, 8000000h
0x18005f0c9  jz      short loc_18005F0D9
0x18005f0cb  test    rsi, rsi
0x18005f0ce  jz      short loc_18005F0D9
0x18005f0d0  mov     [rbp+var_18], 19Ch
0x18005f0d7  jmp     short loc_18005F05F
0x18005f0d9  mov     ecx, ebx
0x18005f0db  shr     ecx, 0Ch
0x18005f0de  and     ecx, 1000h
0x18005f0e4  mov     edx, ecx
0x18005f0e6  or      edx, 8
0x18005f0e9  bt      ebx, 19h
0x18005f0ed  cmovnb  edx, ecx
0x18005f0f0  mov     r14d, edx
0x18005f0f3  or      r14d, 2
0x18005f0f7  bt      ebx, 1Ah
0x18005f0fb  cmovnb  r14d, edx
0x18005f0ff  test    r8d, r8d
0x18005f102  jz      short loc_18005F10F
0x18005f104  test    rsi, rsi
0x18005f107  jz      short loc_18005F10F
0x18005f109  mov     dword ptr [rsi], 1
0x18005f10f  xor     ecx, ecx; dwErrCode
0x18005f111  call    cs:__imp_SetLastError
0x18005f118  nop     dword ptr [rax+rax+00h]
0x18005f11d  mov     rax, [rdi]
0x18005f120  lea     r8, [rbp+var_3C]
0x18005f124  mov     edx, r14d
0x18005f127  mov     rcx, rdi
0x18005f12a  mov     rax, [rax+28h]
0x18005f12e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f133  mov     ebx, eax
0x18005f135  test    eax, eax
0x18005f137  jns     short loc_18005F154
0x18005f139  lea     rdx, byte_18008517D; char *
0x18005f140  mov     ecx, eax; int
0x18005f142  call    ?FusionpTraceCOMFailure@@YAXJPEBDZZ; FusionpTraceCOMFailure(long,char const *,...)
0x18005f147  mov     edx, ebx; int
0x18005f149  lea     rcx, [rbp+var_38]; this
0x18005f14d  call    ?MarkCOMFailure@CFnTracerWin32@@QEAAXJ@Z; CFnTracerWin32::MarkCOMFailure(long)
0x18005f152  jmp     short loc_18005F181
0x18005f154  cmp     [rbp+var_3C], 2
0x18005f158  jnz     short loc_18005F17A
0x18005f15a  mov     ebx, 80070BC2h
0x18005f15f  lea     rcx, [rbp+var_38]; this
0x18005f163  mov     edx, ebx; int
0x18005f165  call    ?MarkCOMFailure@CFnTracerWin32@@QEAAXJ@Z; CFnTracerWin32::MarkCOMFailure(long)
0x18005f16a  mov     edx, ebx; int
0x18005f16c  lea     rcx, off_1800747D0; struct _CALL_SITE_INFO *
0x18005f173  call    ?FusionpTraceCOMFailureOrigination@@YAXAEBU_CALL_SITE_INFO@@J@Z; FusionpTraceCOMFailureOrigination(_CALL_SITE_INFO const &,long)
0x18005f178  jmp     short loc_18005F181
0x18005f17a  mov     [rbp+var_40], 1
0x18005f181  call    cs:__imp_GetLastError
0x18005f188  nop     dword ptr [rax+rax+00h]
0x18005f18d  mov     ebx, eax
0x18005f18f  mov     rcx, rdi
0x18005f192  mov     rax, [rdi]
0x18005f195  mov     rax, [rax+10h]
0x18005f199  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f19e  mov     ecx, ebx; dwErrCode
0x18005f1a0  call    cs:__imp_SetLastError
0x18005f1a7  nop     dword ptr [rax+rax+00h]
0x18005f1ac  mov     ebx, [rbp+var_40]
0x18005f1af  lea     rcx, [rbp+var_38]; this
0x18005f1b3  call    ??1CFnTracerWin32@@QEAA@XZ; CFnTracerWin32::~CFnTracerWin32(void)
0x18005f1b8  mov     eax, ebx
0x18005f1ba  mov     rcx, [rbp+var_8]
0x18005f1be  xor     rcx, rsp; StackCookie
0x18005f1c1  call    __security_check_cookie
0x18005f1c6  lea     r11, [rsp+60h+var_s0]
0x18005f1cb  mov     rbx, [r11+28h]
0x18005f1cf  mov     rsi, [r11+38h]
0x18005f1d3  mov     rsp, r11
0x18005f1d6  pop     r14
0x18005f1d8  pop     rdi
0x18005f1d9  pop     rbp
0x18005f1da  retn
```
