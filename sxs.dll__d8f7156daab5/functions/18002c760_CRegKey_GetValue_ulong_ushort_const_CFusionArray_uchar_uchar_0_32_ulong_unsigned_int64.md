# CRegKey::GetValue(ulong,ushort const *,CFusionArray<uchar,uchar,0,32> &,ulong &,unsigned __int64,...)

- ea: `0x18002c760`
- end: `0x18002c9be`
- name: `?GetValue@CRegKey@@QEAAHKPEBGAEAV?$CFusionArray@EE$0A@$0CA@@@AEAK_KZZ`
- size: `606`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, loader_planting`

## callers

- `0x180023ee0`
- `0x18002bdb4`

## callees

- `0x18000a804`
- `0x18000c000`
- `0x18000df40`
- `0x18000dffc`
- `0x18001c270`
- `0x18002c760`
- `0x18002c9c4`
- `0x18005d2b0`
- `0x18005d38c`
- `0x18006a110`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002c85c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002c88e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002c8fe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002c85c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002c88e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002c8fe`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002c832`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002c832`

## string_xrefs

- `0x18002c991`: `SXS.DLL: %s(%ls)\n`

## pseudocode

```c
__int64 __fastcall CRegKey::GetValue(
        HKEY *a1,
        int a2,
        const wchar_t *a3,
        __int64 a4,
        unsigned int *a5,
        unsigned __int64 a6,
        char a7)
{
  const char *v10; // rcx
  unsigned int v11; // edi
  unsigned int i; // esi
  DWORD v13; // eax
  BYTE *lpData; // rbx
  LSTATUS v15; // eax
  unsigned int v16; // ebx
  char *v18; // rdx
  unsigned __int64 j; // rax
  DWORD cbData; // [rsp+38h] [rbp-41h] BYREF
  DWORD Type; // [rsp+3Ch] [rbp-3Dh] BYREF
  int v23; // [rsp+40h] [rbp-39h] BYREF
  int v24; // [rsp+48h] [rbp-31h] BYREF
  __int64 v25; // [rsp+50h] [rbp-29h]
  __int64 *v26; // [rsp+58h] [rbp-21h]
  __int64 v27; // [rsp+60h] [rbp-19h]
  int v28; // [rsp+68h] [rbp-11h]
  unsigned int *v29; // [rsp+70h] [rbp-9h]

  v26 = &qword_18006DFA8;
  v29 = (unsigned int *)&v23;
  v23 = 0;
  v24 = 1;
  v25 = 0;
  v27 = 544438355;
  v28 = 287;
  CFrame::BaseEnter((CFrame *)&v24);
  Type = 0;
  *a5 = 0;
  if ( (a2 & 0xFFFFFFFE) != 0 )
  {
    v28 = 295;
  }
  else
  {
    if ( a3 )
    {
      v11 = 0;
      for ( i = 0; ; ++i )
      {
        v13 = -1;
        if ( i >= 0xA )
        {
          if ( v11 )
          {
LABEL_25:
            v18 = &a7;
            *a5 = v11;
            for ( j = 0; j < a6; ++j )
            {
              v18 += 8;
              if ( v11 == *((_DWORD *)v18 - 2) )
                break;
            }
            if ( j == a6 )
            {
              FusionpDbgPrintEx(0xC0000000, "SXS.DLL: %s(%ls)\n", "CRegKey::GetValue", a3);
              CFnTracerWin32::MarkWin32Failure((CFnTracerWin32 *)&v24, v11);
              FusionpTraceWin32LastErrorFailureOrigination((const struct _CALL_SITE_INFO *)off_18007CA00);
              goto LABEL_14;
            }
          }
          goto LABEL_13;
        }
        if ( *(_QWORD *)(a4 + 16) <= 0xFFFFFFFF )
          v13 = *(_DWORD *)(a4 + 16);
        lpData = *(BYTE **)(a4 + 8);
        cbData = v13;
        v15 = RegQueryValueExW(*a1, a3, 0, &Type, lpData, &cbData);
        v11 = v15;
        if ( lpData )
          break;
        if ( v15 )
          goto LABEL_9;
        if ( !cbData )
          goto LABEL_13;
        v11 = 234;
LABEL_10:
        SetLastError(0);
        if ( !(unsigned int)CFusionArray<unsigned char,unsigned char,0,32>::Win32SetSize(a4, cbData) )
        {
          *v29 = 0;
          FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_18007CA60);
          goto LABEL_14;
        }
      }
      if ( !v15 )
      {
        if ( (a2 & 1) == 0 && Type != 3 )
        {
          v28 = 338;
          goto LABEL_19;
        }
LABEL_13:
        SetLastError(0);
        *v29 = 1;
        goto LABEL_14;
      }
LABEL_9:
      if ( v15 != 234 )
        goto LABEL_25;
      goto LABEL_10;
    }
    v28 = 296;
  }
LABEL_19:
  FusionpTraceParameterCheck(v10);
  SetLastError(0x57u);
  *v29 = 0;
LABEL_14:
  v16 = *v29;
  CFnTracerWin32::~CFnTracerWin32((CFnTracerWin32 *)&v24);
  return v16;
}

```

## disassembly

```asm
0x18002c760  push    rbp
0x18002c762  push    rbx
0x18002c763  push    rsi
0x18002c764  push    rdi
0x18002c765  push    r12
0x18002c767  push    r13
0x18002c769  push    r14
0x18002c76b  push    r15
0x18002c76d  lea     rbp, [rsp-0Fh]
0x18002c772  sub     rsp, 88h
0x18002c779  mov     rax, cs:__security_cookie
0x18002c780  xor     rax, rsp
0x18002c783  mov     [rbp+47h+var_48], rax
0x18002c787  mov     r13, [rbp+47h+arg_20]
0x18002c78b  lea     rax, qword_18006DFA8
0x18002c792  mov     [rbp+47h+var_68], rax
0x18002c796  xor     ebx, ebx
0x18002c798  lea     rax, [rbp+47h+var_80]
0x18002c79c  mov     [rbp+47h+var_90], rcx
0x18002c7a0  lea     rcx, [rbp+47h+var_78]; this
0x18002c7a4  mov     [rbp+47h+var_50], rax
0x18002c7a8  mov     r14, r9
0x18002c7ab  mov     [rbp+47h+var_80], ebx
0x18002c7ae  mov     r15, r8
0x18002c7b1  mov     [rbp+47h+var_78], 1
0x18002c7b8  mov     r12d, edx
0x18002c7bb  mov     [rbp+47h+var_70], rbx
0x18002c7bf  mov     [rbp+47h+var_60], 20737853h
0x18002c7c7  mov     [rbp+47h+var_58], 11Fh
0x18002c7ce  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x18002c7d3  mov     [rbp+47h+Type], ebx
0x18002c7d6  mov     [r13+0], ebx
0x18002c7da  test    r12d, 0FFFFFFFEh
0x18002c7e1  jnz     loc_18002C8ED
0x18002c7e7  test    r15, r15
0x18002c7ea  jz      loc_18002C912
0x18002c7f0  mov     edi, ebx
0x18002c7f2  mov     esi, ebx
0x18002c7f4  mov     eax, 0FFFFFFFFh
0x18002c7f9  cmp     esi, 0Ah
0x18002c7fc  jnb     loc_18002C94E
0x18002c802  cmp     [r14+10h], rax
0x18002c806  jbe     loc_18002C91B
0x18002c80c  mov     rbx, [r14+8]
0x18002c810  lea     r9, [rbp+47h+Type]; lpType
0x18002c814  mov     [rbp+47h+cbData], eax
0x18002c817  xor     r8d, r8d; lpReserved
0x18002c81a  lea     rax, [rbp+47h+cbData]
0x18002c81e  mov     rdx, r15; lpValueName
0x18002c821  mov     [rsp+0C0h+lpcbData], rax; lpcbData
0x18002c826  mov     rax, [rbp+47h+var_90]
0x18002c82a  mov     [rsp+0C0h+lpData], rbx; lpData
0x18002c82f  mov     rcx, [rax]; hKey
0x18002c832  call    cs:__imp_RegQueryValueExW
0x18002c839  nop     dword ptr [rax+rax+00h]
0x18002c83e  mov     edi, eax
0x18002c840  test    rbx, rbx
0x18002c843  jz      loc_18002C8D6
0x18002c849  xor     ebx, ebx
0x18002c84b  test    eax, eax
0x18002c84d  jz      short loc_18002C882
0x18002c84f  cmp     eax, 0EAh
0x18002c854  jnz     loc_18002C956
0x18002c85a  xor     ecx, ecx; dwErrCode
0x18002c85c  call    cs:__imp_SetLastError
0x18002c863  nop     dword ptr [rax+rax+00h]
0x18002c868  mov     edx, [rbp+47h+cbData]
0x18002c86b  mov     rcx, r14
0x18002c86e  call    ?Win32SetSize@?$CFusionArray@EE$0A@$0CA@@@QEAAH_KW4SetSizeMode@1@@Z; CFusionArray<uchar,uchar,0,32>::Win32SetSize(unsigned __int64,CFusionArray<uchar,uchar,0,32>::SetSizeMode)
0x18002c873  test    eax, eax
0x18002c875  jz      loc_18002C924
0x18002c87b  inc     esi
0x18002c87d  jmp     loc_18002C7F4
0x18002c882  test    r12b, 1
0x18002c886  jz      loc_18002C93B
0x18002c88c  xor     ecx, ecx; dwErrCode
0x18002c88e  call    cs:__imp_SetLastError
0x18002c895  nop     dword ptr [rax+rax+00h]
0x18002c89a  mov     rax, [rbp+47h+var_50]
0x18002c89e  mov     dword ptr [rax], 1
0x18002c8a4  mov     rax, [rbp+47h+var_50]
0x18002c8a8  lea     rcx, [rbp+47h+var_78]; this
0x18002c8ac  mov     ebx, [rax]
0x18002c8ae  call    ??1CFnTracerWin32@@QEAA@XZ; CFnTracerWin32::~CFnTracerWin32(void)
0x18002c8b3  mov     eax, ebx
0x18002c8b5  mov     rcx, [rbp+47h+var_48]
0x18002c8b9  xor     rcx, rsp; StackCookie
0x18002c8bc  call    __security_check_cookie
0x18002c8c1  add     rsp, 88h
0x18002c8c8  pop     r15
0x18002c8ca  pop     r14
0x18002c8cc  pop     r13
0x18002c8ce  pop     r12
0x18002c8d0  pop     rdi
0x18002c8d1  pop     rsi
0x18002c8d2  pop     rbx
0x18002c8d3  pop     rbp
0x18002c8d4  retn
0x18002c8d6  test    eax, eax
0x18002c8d8  jnz     loc_18002C84F
0x18002c8de  cmp     [rbp+47h+cbData], ebx
0x18002c8e1  jz      short loc_18002C88C
0x18002c8e3  mov     edi, 0EAh
0x18002c8e8  jmp     loc_18002C85A
0x18002c8ed  mov     [rbp+47h+var_58], 127h
0x18002c8f4  call    ?FusionpTraceParameterCheck@@YAXPEBD@Z; FusionpTraceParameterCheck(char const *)
0x18002c8f9  mov     ecx, 57h ; 'W'; dwErrCode
0x18002c8fe  call    cs:__imp_SetLastError
0x18002c905  nop     dword ptr [rax+rax+00h]
0x18002c90a  mov     rax, [rbp+47h+var_50]
0x18002c90e  mov     [rax], ebx
0x18002c910  jmp     short loc_18002C8A4
0x18002c912  mov     [rbp+47h+var_58], 128h
0x18002c919  jmp     short loc_18002C8F4
0x18002c91b  mov     eax, [r14+10h]
0x18002c91f  jmp     loc_18002C80C
0x18002c924  mov     rax, [rbp+47h+var_50]
0x18002c928  lea     rcx, off_18007CA60; struct _CALL_SITE_INFO *
0x18002c92f  mov     [rax], ebx
0x18002c931  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x18002c936  jmp     loc_18002C8A4
0x18002c93b  cmp     [rbp+47h+Type], 3
0x18002c93f  jz      loc_18002C88C
0x18002c945  mov     [rbp+47h+var_58], 152h
0x18002c94c  jmp     short loc_18002C8F4
0x18002c94e  test    edi, edi
0x18002c950  jz      loc_18002C88C
0x18002c956  mov     rcx, [rbp+47h+arg_28]
0x18002c95a  lea     rdx, [rbp+47h+arg_30]
0x18002c961  mov     [r13+0], edi
0x18002c965  mov     rax, rbx
0x18002c968  test    rcx, rcx
0x18002c96b  jz      short loc_18002C97E
0x18002c96d  lea     rdx, [rdx+8]
0x18002c971  cmp     edi, [rdx-8]
0x18002c974  jz      short loc_18002C97E
0x18002c976  inc     rax
0x18002c979  cmp     rax, rcx
0x18002c97c  jb      short loc_18002C96D
0x18002c97e  cmp     rax, rcx
0x18002c981  jnz     loc_18002C88C
0x18002c987  mov     r9, r15
0x18002c98a  lea     r8, aCregkeyGetvalu; "CRegKey::GetValue"
0x18002c991  lea     rdx, aSxsDllSLs; "SXS.DLL: %s(%ls)\n"
0x18002c998  mov     ecx, 0C0000000h; unsigned int
0x18002c99d  call    ?FusionpDbgPrintEx@@YAKKPEBDZZ; FusionpDbgPrintEx(ulong,char const *,...)
0x18002c9a2  mov     edx, edi; unsigned int
0x18002c9a4  lea     rcx, [rbp+47h+var_78]; this
0x18002c9a8  call    ?MarkWin32Failure@CFnTracerWin32@@QEAAXK@Z; CFnTracerWin32::MarkWin32Failure(ulong)
0x18002c9ad  lea     rcx, off_18007CA00; struct _CALL_SITE_INFO *
0x18002c9b4  call    ?FusionpTraceWin32LastErrorFailureOrigination@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailureOrigination(_CALL_SITE_INFO const &)
0x18002c9b9  jmp     loc_18002C8A4
```
