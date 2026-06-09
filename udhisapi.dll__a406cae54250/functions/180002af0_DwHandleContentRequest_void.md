# DwHandleContentRequest(void *)

- ea: `0x180002af0`
- end: `0x180002de4`
- name: `?DwHandleContentRequest@@YAKPEAX@Z`
- size: `756`
- prototype: `__int64 __fastcall(struct _EXTENSION_CONTROL_BLOCK *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180002110`

## callees

- `0x180001400`
- `0x180002884`
- `0x180002af0`
- `0x180002dec`
- `0x180002f08`
- `0x180003788`
- `0x1800037d8`
- `0x180003854`
- `0x1800038ec`
- `0x18000c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x180002b67`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x180002b7f`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x180002b67`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x180002b7f`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180002c74`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180002c74`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180002cab`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180002cab`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180002d0b`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180002d0b`

## pseudocode

```c
__int64 __fastcall DwHandleContentRequest(struct _EXTENSION_CONTROL_BLOCK *a1)
{
  HCONN ConnID; // rcx
  BOOL (__stdcall *ServerSupportFunction)(HCONN, DWORD, LPVOID, LPDWORD, LPDWORD); // rax
  LPSTR lpszMethod; // rbx
  HCONN v5; // r15
  unsigned int v6; // r12d
  _QWORD *v7; // rcx
  HRESULT v8; // eax
  int v9; // ebx
  HRESULT Instance; // eax
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rdx
  const char *v14; // rax
  int v16; // [rsp+30h] [rbp-68h] BYREF
  struct IUPnPDynamicContentSource *ppv; // [rsp+38h] [rbp-60h] BYREF
  struct _GUID v18; // [rsp+40h] [rbp-58h] BYREF

  v16 = 0;
  ConnID = a1->ConnID;
  ServerSupportFunction = a1->ServerSupportFunction;
  v18 = 0;
  ((void (__fastcall *)(HCONN, __int64, int *, _QWORD, _QWORD))ServerSupportFunction)(ConnID, 1008, &v16, 0, 0);
  lpszMethod = a1->lpszMethod;
  v5 = a1->ConnID;
  v6 = (v16 != 0) + 1;
  if ( !(unsigned int)_o__stricmp(lpszMethod, "GET") || !(unsigned int)_o__stricmp(lpszMethod, "HEAD") )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      WPP_SF_qs(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        21,
        (unsigned int)WPP_8a4b82c67137342c730f9db1111c400e_Traceguids,
        (_DWORD)v5,
        (__int64)a1->lpszQueryString);
    v8 = HrParseDescriptionQueryString(a1->lpszQueryString, &v18);
    v9 = v8;
    if ( v8 < 0 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
        goto LABEL_27;
      v12 = 24;
    }
    else
    {
      v8 = CoInitializeEx(0, 0);
      v9 = v8;
      if ( v8 >= 0 )
      {
        ppv = 0;
        Instance = CoCreateInstance(
                     &CLSID_UPnPDynamicContentSource,
                     0,
                     1u,
                     &IID_IUPnPDynamicContentSource,
                     (LPVOID *)&ppv);
        v9 = Instance;
        if ( Instance < 0 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
          {
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              22,
              WPP_8a4b82c67137342c730f9db1111c400e_Traceguids,
              v5,
              Instance);
          }
        }
        else
        {
          v9 = HrReturnContent(a1, ppv, &v18);
          (*(void (__fastcall **)(struct IUPnPDynamicContentSource *))(*(_QWORD *)ppv + 16LL))(ppv);
        }
        CoUninitialize();
LABEL_27:
        if ( v9 >= 0 )
          return v6;
        goto LABEL_28;
      }
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
        goto LABEL_27;
      v12 = 23;
    }
    WPP_SF_qD(v11[2], v12, WPP_8a4b82c67137342c730f9db1111c400e_Traceguids, v5, v8);
    goto LABEL_27;
  }
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        (unsigned int)WPP_8a4b82c67137342c730f9db1111c400e_Traceguids,
        (unsigned int)"HrValidateDescriptionMethod(): Exiting",
        5);
      v7 = WPP_GLOBAL_Control;
    }
    if ( v7 != &WPP_GLOBAL_Control && (*((_DWORD *)v7 + 7) & 0x400) != 0 )
      WPP_SF_qsD(
        v7[2],
        25,
        (unsigned int)WPP_8a4b82c67137342c730f9db1111c400e_Traceguids,
        (_DWORD)v5,
        (__int64)a1->lpszMethod,
        5);
  }
LABEL_28:
  v13 = 0x7FFFFFFF;
  v14 = "\r\n";
  do
  {
    if ( !*v14 )
      break;
    ++v14;
    --v13;
  }
  while ( v13 );
  v6 = 4;
  if ( (unsigned int)bSendResponseToClient(
                       a1,
                       "500 Internal Server Error",
                       v13 != 0 ? 0x7FFFFFFF - v13 : 0,
                       "\r\n",
                       0,
                       0) )
    a1->dwHttpStatusCode = 500;
  return v6;
}

```

## disassembly

```asm
0x180002af0  push    rbx
0x180002af2  push    rsi
0x180002af3  push    rdi
0x180002af4  push    r12
0x180002af6  push    r14
0x180002af8  push    r15
0x180002afa  sub     rsp, 68h
0x180002afe  mov     rax, cs:__security_cookie
0x180002b05  xor     rax, rsp
0x180002b08  mov     [rsp+98h+var_48], rax
0x180002b0d  mov     r14, rcx
0x180002b10  mov     [rsp+98h+var_68], 0
0x180002b18  mov     rcx, [rcx+8]
0x180002b1c  lea     r8, [rsp+98h+var_68]
0x180002b21  xorps   xmm0, xmm0
0x180002b24  mov     [rsp+98h+ppv], 0
0x180002b2d  xor     r9d, r9d
0x180002b30  mov     edx, 3F0h
0x180002b35  mov     rax, [r14+0B8h]
0x180002b3c  movups  xmmword ptr [rsp+98h+var_58.Data1], xmm0
0x180002b41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b46  mov     eax, [rsp+98h+var_68]
0x180002b4a  lea     rdx, aGet; "GET"
0x180002b51  mov     rbx, [r14+68h]
0x180002b55  neg     eax
0x180002b57  mov     r15, [r14+8]
0x180002b5b  mov     rcx, rbx
0x180002b5e  sbb     r12d, r12d
0x180002b61  neg     r12d
0x180002b64  inc     r12d
0x180002b67  call    cs:__imp__o__stricmp
0x180002b6d  test    eax, eax
0x180002b6f  jz      loc_180002C1A
0x180002b75  lea     rdx, aHead; "HEAD"
0x180002b7c  mov     rcx, rbx
0x180002b7f  call    cs:__imp__o__stricmp
0x180002b85  test    eax, eax
0x180002b87  jz      loc_180002C1A
0x180002b8d  mov     rcx, cs:WPP_GLOBAL_Control
0x180002b94  lea     rdi, WPP_GLOBAL_Control
0x180002b9b  cmp     rcx, rdi
0x180002b9e  jz      loc_180002D5C
0x180002ba4  test    byte ptr [rcx+1Ch], 1
0x180002ba8  jz      short loc_180002BD5
0x180002baa  mov     rcx, [rcx+10h]
0x180002bae  lea     r9, aHrvalidatedesc; "HrValidateDescriptionMethod(): Exiting"
0x180002bb5  mov     edx, 0Ah
0x180002bba  mov     dword ptr [rsp+98h+ppv], 80004005h
0x180002bc2  lea     r8, WPP_8a4b82c67137342c730f9db1111c400e_Traceguids
0x180002bc9  call    WPP_SF_sd
0x180002bce  mov     rcx, cs:WPP_GLOBAL_Control
0x180002bd5  cmp     rcx, rdi
0x180002bd8  jz      loc_180002D5C
0x180002bde  mov     esi, 400h
0x180002be3  test    [rcx+1Ch], esi
0x180002be6  jz      loc_180002D5C
0x180002bec  mov     rax, [r14+68h]
0x180002bf0  lea     r8, WPP_8a4b82c67137342c730f9db1111c400e_Traceguids
0x180002bf7  mov     rcx, [rcx+10h]
0x180002bfb  mov     edx, 19h
0x180002c00  mov     dword ptr [rsp+98h+var_70], 80004005h
0x180002c08  mov     r9, r15
0x180002c0b  mov     [rsp+98h+ppv], rax
0x180002c10  call    WPP_SF_qsD
0x180002c15  jmp     loc_180002D5C
0x180002c1a  mov     rcx, cs:WPP_GLOBAL_Control
0x180002c21  lea     rdi, WPP_GLOBAL_Control
0x180002c28  mov     esi, 400h
0x180002c2d  cmp     rcx, rdi
0x180002c30  jz      short loc_180002C58
0x180002c32  test    [rcx+1Ch], esi
0x180002c35  jz      short loc_180002C58
0x180002c37  mov     rax, [r14+70h]
0x180002c3b  lea     r8, WPP_8a4b82c67137342c730f9db1111c400e_Traceguids
0x180002c42  mov     rcx, [rcx+10h]
0x180002c46  mov     edx, 15h
0x180002c4b  mov     r9, r15
0x180002c4e  mov     [rsp+98h+ppv], rax
0x180002c53  call    WPP_SF_qs
0x180002c58  mov     rcx, [r14+70h]; char *
0x180002c5c  lea     rdx, [rsp+98h+var_58]; struct _GUID *
0x180002c61  call    ?HrParseDescriptionQueryString@@YAJPEADAEAU_GUID@@@Z; HrParseDescriptionQueryString(char *,_GUID &)
0x180002c66  mov     ebx, eax
0x180002c68  test    eax, eax
0x180002c6a  js      loc_180002D2B
0x180002c70  xor     edx, edx; dwCoInit
0x180002c72  xor     ecx, ecx; pvReserved
0x180002c74  call    cs:__imp_CoInitializeEx
0x180002c7a  mov     ebx, eax
0x180002c7c  test    eax, eax
0x180002c7e  js      loc_180002D13
0x180002c84  xor     edx, edx; pUnkOuter
0x180002c86  mov     [rsp+98h+var_60], 0
0x180002c8f  lea     rax, [rsp+98h+var_60]
0x180002c94  lea     r9, IID_IUPnPDynamicContentSource; riid
0x180002c9b  mov     [rsp+98h+ppv], rax; ppv
0x180002ca0  lea     rcx, CLSID_UPnPDynamicContentSource; rclsid
0x180002ca7  lea     r8d, [rdx+1]; dwClsContext
0x180002cab  call    cs:__imp_CoCreateInstance
0x180002cb1  mov     ebx, eax
0x180002cb3  test    eax, eax
0x180002cb5  js      short loc_180002CDE
0x180002cb7  mov     rdx, [rsp+98h+var_60]; struct IUPnPDynamicContentSource *
0x180002cbc  lea     r8, [rsp+98h+var_58]; struct _GUID *
0x180002cc1  mov     rcx, r14; struct _EXTENSION_CONTROL_BLOCK *
0x180002cc4  call    ?HrReturnContent@@YAJPEAU_EXTENSION_CONTROL_BLOCK@@PEAUIUPnPDynamicContentSource@@AEBU_GUID@@@Z; HrReturnContent(_EXTENSION_CONTROL_BLOCK *,IUPnPDynamicContentSource *,_GUID const &)
0x180002cc9  mov     rcx, [rsp+98h+var_60]
0x180002cce  mov     ebx, eax
0x180002cd0  mov     rax, [rcx]
0x180002cd3  mov     rax, [rax+10h]
0x180002cd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002cdc  jmp     short loc_180002D0B
0x180002cde  mov     rcx, cs:WPP_GLOBAL_Control
0x180002ce5  cmp     rcx, rdi
0x180002ce8  jz      short loc_180002D0B
0x180002cea  test    [rcx+1Ch], esi
0x180002ced  jz      short loc_180002D0B
0x180002cef  mov     rcx, [rcx+10h]
0x180002cf3  lea     r8, WPP_8a4b82c67137342c730f9db1111c400e_Traceguids
0x180002cfa  mov     edx, 16h
0x180002cff  mov     dword ptr [rsp+98h+ppv], eax
0x180002d03  mov     r9, r15
0x180002d06  call    WPP_SF_qD
0x180002d0b  call    cs:__imp_CoUninitialize
0x180002d11  jmp     short loc_180002D58
0x180002d13  mov     rcx, cs:WPP_GLOBAL_Control
0x180002d1a  cmp     rcx, rdi
0x180002d1d  jz      short loc_180002D58
0x180002d1f  test    [rcx+1Ch], esi
0x180002d22  jz      short loc_180002D58
0x180002d24  mov     edx, 17h
0x180002d29  jmp     short loc_180002D41
0x180002d2b  mov     rcx, cs:WPP_GLOBAL_Control
0x180002d32  cmp     rcx, rdi
0x180002d35  jz      short loc_180002D58
0x180002d37  test    [rcx+1Ch], esi
0x180002d3a  jz      short loc_180002D58
0x180002d3c  mov     edx, 18h
0x180002d41  mov     rcx, [rcx+10h]
0x180002d45  lea     r8, WPP_8a4b82c67137342c730f9db1111c400e_Traceguids
0x180002d4c  mov     r9, r15
0x180002d4f  mov     dword ptr [rsp+98h+ppv], eax
0x180002d53  call    WPP_SF_qD
0x180002d58  test    ebx, ebx
0x180002d5a  jns     short loc_180002DC6
0x180002d5c  mov     r8d, 7FFFFFFFh
0x180002d62  lea     r9, asc_18000D924; "\r\n"
0x180002d69  mov     edx, r8d
0x180002d6c  mov     rax, r9
0x180002d6f  cmp     byte ptr [rax], 0
0x180002d72  jz      short loc_180002D7D
0x180002d74  inc     rax
0x180002d77  sub     rdx, 1
0x180002d7b  jnz     short loc_180002D6F
0x180002d7d  sub     r8d, edx
0x180002d80  mov     [rsp+98h+var_70], 0; char *
0x180002d89  mov     rax, rdx
0x180002d8c  mov     dword ptr [rsp+98h+ppv], 0; unsigned int
0x180002d94  neg     rax
0x180002d97  mov     r12d, 4
0x180002d9d  sbb     ecx, ecx
0x180002d9f  and     ecx, r8d
0x180002da2  neg     rdx
0x180002da5  lea     rdx, a500InternalSer; "500 Internal Server Error"
0x180002dac  sbb     r8d, r8d
0x180002daf  and     r8d, ecx; unsigned int
0x180002db2  mov     rcx, r14; struct _EXTENSION_CONTROL_BLOCK *
0x180002db5  call    ?bSendResponseToClient@@YAHPEAU_EXTENSION_CONTROL_BLOCK@@PEBDK1K1@Z; bSendResponseToClient(_EXTENSION_CONTROL_BLOCK *,char const *,ulong,char const *,ulong,char const *)
0x180002dba  test    eax, eax
0x180002dbc  jz      short loc_180002DC6
0x180002dbe  mov     dword ptr [r14+10h], 1F4h
0x180002dc6  mov     eax, r12d
0x180002dc9  mov     rcx, [rsp+98h+var_48]
0x180002dce  xor     rcx, rsp; StackCookie
0x180002dd1  call    __security_check_cookie
0x180002dd6  add     rsp, 68h
0x180002dda  pop     r15
0x180002ddc  pop     r14
0x180002dde  pop     r12
0x180002de0  pop     rdi
0x180002de1  pop     rsi
0x180002de2  pop     rbx
0x180002de3  retn
```
