# DwHandleControlRequest(void *)

- ea: `0x180003aa0`
- end: `0x180003da6`
- name: `?DwHandleControlRequest@@YAKPEAX@Z`
- size: `774`
- prototype: `__int64 __fastcall(struct _EXTENSION_CONTROL_BLOCK *)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800026a4`
- `0x180002884`
- `0x180003788`
- `0x1800037d8`
- `0x180003854`
- `0x1800038ec`
- `0x180003aa0`
- `0x18000512c`
- `0x18000c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x180003b03`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x180003b1b`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x180003b33`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x180003b47`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x180003b03`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x180003b1b`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x180003b33`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x180003b47`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180003c20`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180003c20`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180003c36`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180003c36`

## pseudocode

```c
__int64 __fastcall DwHandleControlRequest(struct _EXTENSION_CONTROL_BLOCK *a1)
{
  LPSTR lpszMethod; // rbx
  HCONN ConnID; // r14
  unsigned int v4; // r15d
  int v5; // eax
  int v6; // ebx
  _QWORD *v7; // rcx
  HRESULT v8; // eax
  unsigned int v9; // edx
  __int64 v10; // r8
  const char *v11; // rax
  const char *v12; // rax
  int v14; // [rsp+50h] [rbp+8h] BYREF

  v14 = 0;
  ((void (__fastcall *)(HCONN, __int64, int *, _QWORD, _QWORD))a1->ServerSupportFunction)(a1->ConnID, 1008, &v14, 0, 0);
  lpszMethod = a1->lpszMethod;
  ConnID = a1->ConnID;
  v4 = (v14 != 0) + 1;
  if ( (unsigned int)_o__stricmp(lpszMethod, "POST") && (unsigned int)_o__stricmp(lpszMethod, "M-POST") )
  {
    if ( !(unsigned int)_o__stricmp(lpszMethod, "GET") || (v5 = _o__stricmp(lpszMethod, "HEAD"), v6 = -2147180029, !v5) )
      v6 = -2147180028;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          10,
          (unsigned int)WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids,
          (unsigned int)"HrValidateControlMethod(): Exiting",
          v6);
        v7 = WPP_GLOBAL_Control;
      }
      if ( v7 != &WPP_GLOBAL_Control && (*((_DWORD *)v7 + 7) & 0x400) != 0 )
        WPP_SF_qsD(
          v7[2],
          106,
          (unsigned int)WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids,
          (_DWORD)ConnID,
          (__int64)a1->lpszMethod,
          v6);
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      WPP_SF_qs(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        104,
        (unsigned int)WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids,
        (_DWORD)ConnID,
        (__int64)a1->lpszQueryString);
    v8 = CoInitializeEx(0, 0);
    v6 = v8;
    if ( v8 < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 105, WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids, ConnID, v8);
    }
    else
    {
      v6 = HrDoRequestAndReturnResponse(a1);
      CoUninitialize();
    }
    if ( v6 >= 0 )
      return v4;
  }
  if ( (unsigned int)(v6 + 2147180031) <= 1 )
    goto LABEL_38;
  switch ( v6 )
  {
    case -2147180032:
      v9 = 415;
LABEL_39:
      SendSimpleResponse(a1, v9);
      return v4;
    case -2147180027:
LABEL_38:
      v9 = 400;
      goto LABEL_39;
    case -2147180029:
      v9 = 501;
      goto LABEL_39;
  }
  v10 = 0x7FFFFFFF;
  if ( v6 == -2147180028 )
  {
    v11 = "Allow: POST, M-POST\r\n\r\n";
    do
    {
      if ( !*v11 )
        break;
      ++v11;
      --v10;
    }
    while ( v10 );
    if ( (unsigned int)bSendResponseToClient(
                         a1,
                         "405 Method Not Allowed",
                         v10 != 0 ? 0x7FFFFFFF - v10 : 0,
                         "Allow: POST, M-POST\r\n\r\n",
                         0,
                         0) )
      a1->dwHttpStatusCode = 405;
  }
  else
  {
    v12 = "\r\n";
    do
    {
      if ( !*v12 )
        break;
      ++v12;
      --v10;
    }
    while ( v10 );
    v4 = 4;
    if ( (unsigned int)bSendResponseToClient(
                         a1,
                         "500 Internal Server Error",
                         v10 != 0 ? 0x7FFFFFFF - v10 : 0,
                         "\r\n",
                         0,
                         0) )
      a1->dwHttpStatusCode = 500;
  }
  return v4;
}

```

## disassembly

```asm
0x180003aa0  mov     rax, rsp
0x180003aa3  mov     [rax+10h], rbx
0x180003aa7  mov     [rax+18h], rsi
0x180003aab  push    rdi
0x180003aac  push    r14
0x180003aae  push    r15
0x180003ab0  sub     rsp, 30h
0x180003ab4  mov     rdi, rcx
0x180003ab7  mov     dword ptr [rax+8], 0
0x180003abe  mov     rcx, [rcx+8]
0x180003ac2  lea     r8, [rax+8]
0x180003ac6  mov     qword ptr [rax-28h], 0
0x180003ace  xor     r9d, r9d
0x180003ad1  mov     edx, 3F0h
0x180003ad6  mov     rax, [rdi+0B8h]
0x180003add  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ae2  mov     eax, [rsp+48h+arg_0]
0x180003ae6  lea     rdx, aPost; "POST"
0x180003aed  mov     rbx, [rdi+68h]
0x180003af1  neg     eax
0x180003af3  mov     r14, [rdi+8]
0x180003af7  mov     rcx, rbx
0x180003afa  sbb     r15d, r15d
0x180003afd  neg     r15d
0x180003b00  inc     r15d
0x180003b03  call    cs:__imp__o__stricmp
0x180003b09  test    eax, eax
0x180003b0b  jz      loc_180003BDF
0x180003b11  lea     rdx, aMPost; "M-POST"
0x180003b18  mov     rcx, rbx
0x180003b1b  call    cs:__imp__o__stricmp
0x180003b21  test    eax, eax
0x180003b23  jz      loc_180003BDF
0x180003b29  lea     rdx, aGet; "GET"
0x180003b30  mov     rcx, rbx
0x180003b33  call    cs:__imp__o__stricmp
0x180003b39  test    eax, eax
0x180003b3b  jz      short loc_180003B56
0x180003b3d  lea     rdx, aHead; "HEAD"
0x180003b44  mov     rcx, rbx
0x180003b47  call    cs:__imp__o__stricmp
0x180003b4d  mov     ebx, 8004A203h
0x180003b52  test    eax, eax
0x180003b54  jnz     short loc_180003B5B
0x180003b56  mov     ebx, 8004A204h
0x180003b5b  mov     rcx, cs:WPP_GLOBAL_Control
0x180003b62  lea     rsi, WPP_GLOBAL_Control
0x180003b69  cmp     rcx, rsi
0x180003b6c  jz      loc_180003C77
0x180003b72  test    byte ptr [rcx+1Ch], 1
0x180003b76  jz      short loc_180003B9F
0x180003b78  mov     rcx, [rcx+10h]
0x180003b7c  lea     r9, aHrvalidatecont_2; "HrValidateControlMethod(): Exiting"
0x180003b83  mov     edx, 0Ah
0x180003b88  mov     [rsp+48h+var_28], ebx
0x180003b8c  lea     r8, WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids
0x180003b93  call    WPP_SF_sd
0x180003b98  mov     rcx, cs:WPP_GLOBAL_Control
0x180003b9f  cmp     rcx, rsi
0x180003ba2  jz      loc_180003C77
0x180003ba8  test    dword ptr [rcx+1Ch], 400h
0x180003baf  jz      loc_180003C77
0x180003bb5  mov     rax, [rdi+68h]
0x180003bb9  lea     r8, WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids
0x180003bc0  mov     rcx, [rcx+10h]
0x180003bc4  mov     edx, 6Ah ; 'j'
0x180003bc9  mov     dword ptr [rsp+48h+var_20], ebx
0x180003bcd  mov     r9, r14
0x180003bd0  mov     qword ptr [rsp+48h+var_28], rax
0x180003bd5  call    WPP_SF_qsD
0x180003bda  jmp     loc_180003C77
0x180003bdf  mov     rcx, cs:WPP_GLOBAL_Control
0x180003be6  lea     rsi, WPP_GLOBAL_Control
0x180003bed  cmp     rcx, rsi
0x180003bf0  jz      short loc_180003C1C
0x180003bf2  test    dword ptr [rcx+1Ch], 400h
0x180003bf9  jz      short loc_180003C1C
0x180003bfb  mov     rax, [rdi+70h]
0x180003bff  lea     r8, WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids
0x180003c06  mov     rcx, [rcx+10h]
0x180003c0a  mov     edx, 68h ; 'h'
0x180003c0f  mov     r9, r14
0x180003c12  mov     qword ptr [rsp+48h+var_28], rax
0x180003c17  call    WPP_SF_qs
0x180003c1c  xor     edx, edx; dwCoInit
0x180003c1e  xor     ecx, ecx; pvReserved
0x180003c20  call    cs:__imp_CoInitializeEx
0x180003c26  mov     ebx, eax
0x180003c28  test    eax, eax
0x180003c2a  js      short loc_180003C3E
0x180003c2c  mov     rcx, rdi; struct _EXTENSION_CONTROL_BLOCK *
0x180003c2f  call    ?HrDoRequestAndReturnResponse@@YAJPEAU_EXTENSION_CONTROL_BLOCK@@@Z; HrDoRequestAndReturnResponse(_EXTENSION_CONTROL_BLOCK *)
0x180003c34  mov     ebx, eax
0x180003c36  call    cs:__imp_CoUninitialize
0x180003c3c  jmp     short loc_180003C6F
0x180003c3e  mov     rcx, cs:WPP_GLOBAL_Control
0x180003c45  cmp     rcx, rsi
0x180003c48  jz      short loc_180003C6F
0x180003c4a  test    dword ptr [rcx+1Ch], 400h
0x180003c51  jz      short loc_180003C6F
0x180003c53  mov     rcx, [rcx+10h]
0x180003c57  lea     r8, WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids
0x180003c5e  mov     edx, 69h ; 'i'
0x180003c63  mov     [rsp+48h+var_28], eax
0x180003c67  mov     r9, r14
0x180003c6a  call    WPP_SF_qD
0x180003c6f  test    ebx, ebx
0x180003c71  jns     loc_180003D8F
0x180003c77  lea     eax, [rbx+7FFB5DFFh]
0x180003c7d  cmp     eax, 1
0x180003c80  jbe     loc_180003D82
0x180003c86  cmp     ebx, 8004A200h
0x180003c8c  jnz     short loc_180003C98
0x180003c8e  mov     edx, 19Fh
0x180003c93  jmp     loc_180003D87
0x180003c98  cmp     ebx, 8004A205h
0x180003c9e  jz      loc_180003D82
0x180003ca4  cmp     ebx, 8004A203h
0x180003caa  jnz     short loc_180003CB6
0x180003cac  mov     edx, 1F5h
0x180003cb1  jmp     loc_180003D87
0x180003cb6  mov     edx, 7FFFFFFFh
0x180003cbb  mov     r8d, edx
0x180003cbe  cmp     ebx, 8004A204h
0x180003cc4  jnz     short loc_180003D21
0x180003cc6  lea     r9, aAllowPostMPost; "Allow: POST, M-POST\r\n\r\n"
0x180003ccd  mov     rax, r9
0x180003cd0  cmp     byte ptr [rax], 0
0x180003cd3  jz      short loc_180003CDE
0x180003cd5  inc     rax
0x180003cd8  sub     r8, 1
0x180003cdc  jnz     short loc_180003CD0
0x180003cde  sub     edx, r8d
0x180003ce1  mov     [rsp+48h+var_20], 0; char *
0x180003cea  mov     rax, r8
0x180003ced  mov     [rsp+48h+var_28], 0; unsigned int
0x180003cf5  neg     rax
0x180003cf8  sbb     ecx, ecx
0x180003cfa  and     ecx, edx
0x180003cfc  lea     rdx, a405MethodNotAl; "405 Method Not Allowed"
0x180003d03  neg     r8
0x180003d06  sbb     r8d, r8d
0x180003d09  and     r8d, ecx; unsigned int
0x180003d0c  mov     rcx, rdi; struct _EXTENSION_CONTROL_BLOCK *
0x180003d0f  call    ?bSendResponseToClient@@YAHPEAU_EXTENSION_CONTROL_BLOCK@@PEBDK1K1@Z; bSendResponseToClient(_EXTENSION_CONTROL_BLOCK *,char const *,ulong,char const *,ulong,char const *)
0x180003d14  test    eax, eax
0x180003d16  jz      short loc_180003D8F
0x180003d18  mov     dword ptr [rdi+10h], 195h
0x180003d1f  jmp     short loc_180003D8F
0x180003d21  lea     r9, asc_18000D924; "\r\n"
0x180003d28  mov     rax, r9
0x180003d2b  cmp     byte ptr [rax], 0
0x180003d2e  jz      short loc_180003D39
0x180003d30  inc     rax
0x180003d33  sub     r8, 1
0x180003d37  jnz     short loc_180003D2B
0x180003d39  sub     edx, r8d
0x180003d3c  mov     [rsp+48h+var_20], 0; char *
0x180003d45  mov     rax, r8
0x180003d48  mov     [rsp+48h+var_28], 0; unsigned int
0x180003d50  neg     rax
0x180003d53  mov     r15d, 4
0x180003d59  sbb     ecx, ecx
0x180003d5b  and     ecx, edx
0x180003d5d  lea     rdx, a500InternalSer; "500 Internal Server Error"
0x180003d64  neg     r8
0x180003d67  sbb     r8d, r8d
0x180003d6a  and     r8d, ecx; unsigned int
0x180003d6d  mov     rcx, rdi; struct _EXTENSION_CONTROL_BLOCK *
0x180003d70  call    ?bSendResponseToClient@@YAHPEAU_EXTENSION_CONTROL_BLOCK@@PEBDK1K1@Z; bSendResponseToClient(_EXTENSION_CONTROL_BLOCK *,char const *,ulong,char const *,ulong,char const *)
0x180003d75  test    eax, eax
0x180003d77  jz      short loc_180003D8F
0x180003d79  mov     dword ptr [rdi+10h], 1F4h
0x180003d80  jmp     short loc_180003D8F
0x180003d82  mov     edx, 190h; unsigned int
0x180003d87  mov     rcx, rdi; struct _EXTENSION_CONTROL_BLOCK *
0x180003d8a  call    ?SendSimpleResponse@@YAXPEAU_EXTENSION_CONTROL_BLOCK@@K@Z; SendSimpleResponse(_EXTENSION_CONTROL_BLOCK *,ulong)
0x180003d8f  mov     rbx, [rsp+48h+arg_8]
0x180003d94  mov     eax, r15d
0x180003d97  mov     rsi, [rsp+48h+arg_10]
0x180003d9c  add     rsp, 30h
0x180003da0  pop     r15
0x180003da2  pop     r14
0x180003da4  pop     rdi
0x180003da5  retn
```
