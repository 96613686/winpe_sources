# DwHandleEventRequest(void *)

- ea: `0x180006e40`
- end: `0x180006f5d`
- name: `?DwHandleEventRequest@@YAKPEAX@Z`
- size: `285`
- prototype: `__int64 __fastcall(struct _EXTENSION_CONTROL_BLOCK *)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002504`
- `0x1800026a4`
- `0x180006e40`
- `0x1800071bc`
- `0x180007734`
- `0x18000c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x180006eab`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x180006eca`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x180006eab`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x180006eca`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180006e51`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180006e51`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180006efc`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180006efc`

## pseudocode

```c
__int64 __fastcall DwHandleEventRequest(struct _EXTENSION_CONTROL_BLOCK *a1)
{
  LPSTR lpszMethod; // r9
  unsigned int v3; // ebx
  unsigned int v4; // eax
  HCONN ConnID; // rcx
  BOOL (__stdcall *ServerSupportFunction)(HCONN, DWORD, LPVOID, LPDWORD, LPDWORD); // rax
  int v8; // [rsp+40h] [rbp+8h] BYREF

  if ( CoInitializeEx(0, 0) >= 0 )
  {
    lpszMethod = a1->lpszMethod;
    v3 = 1;
    if ( !lpszMethod )
      goto LABEL_14;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_604df09e42be3037ea2c3a056a88862f_Traceguids, lpszMethod);
    if ( (unsigned int)_o__stricmp(a1->lpszMethod, "SUBSCRIBE") )
    {
      if ( (unsigned int)_o__stricmp(a1->lpszMethod, "UNSUBSCRIBE") )
      {
        a1->dwHttpStatusCode = 400;
        v3 = 4;
LABEL_13:
        SendSimpleResponse(a1, a1->dwHttpStatusCode);
LABEL_14:
        CoUninitialize();
        if ( v3 == 4 )
          return v3;
        goto LABEL_17;
      }
      v4 = DwHandleUnSubscribeMethod(a1);
    }
    else
    {
      v4 = DwHandleSubscribeMethod(a1);
    }
    v3 = v4;
    if ( v4 != 4 )
      goto LABEL_14;
    goto LABEL_13;
  }
  SendSimpleResponse(a1, 0x1F4u);
LABEL_17:
  ConnID = a1->ConnID;
  ServerSupportFunction = a1->ServerSupportFunction;
  v8 = 0;
  ((void (__fastcall *)(HCONN, __int64, int *, _QWORD, _QWORD))ServerSupportFunction)(ConnID, 1008, &v8, 0, 0);
  return (unsigned int)(v8 != 0) + 1;
}

```

## disassembly

```asm
0x180006e40  mov     [rsp+arg_8], rbx
0x180006e45  push    rdi
0x180006e46  sub     rsp, 30h
0x180006e4a  mov     rdi, rcx
0x180006e4d  xor     edx, edx; dwCoInit
0x180006e4f  xor     ecx, ecx; pvReserved
0x180006e51  call    cs:__imp_CoInitializeEx
0x180006e57  test    eax, eax
0x180006e59  js      loc_180006F09
0x180006e5f  mov     r9, [rdi+68h]
0x180006e63  mov     ebx, 1
0x180006e68  test    r9, r9
0x180006e6b  jz      loc_180006EFC
0x180006e71  mov     rcx, cs:WPP_GLOBAL_Control
0x180006e78  lea     rax, WPP_GLOBAL_Control
0x180006e7f  cmp     rcx, rax
0x180006e82  jz      short loc_180006EA0
0x180006e84  test    dword ptr [rcx+1Ch], 400h
0x180006e8b  jz      short loc_180006EA0
0x180006e8d  mov     rcx, [rcx+10h]
0x180006e91  lea     edx, [rbx+9]
0x180006e94  lea     r8, WPP_604df09e42be3037ea2c3a056a88862f_Traceguids
0x180006e9b  call    WPP_SF_s
0x180006ea0  mov     rcx, [rdi+68h]
0x180006ea4  lea     rdx, aSubscribe; "SUBSCRIBE"
0x180006eab  call    cs:__imp__o__stricmp
0x180006eb1  test    eax, eax
0x180006eb3  jnz     short loc_180006EBF
0x180006eb5  mov     rcx, rdi; struct _EXTENSION_CONTROL_BLOCK *
0x180006eb8  call    ?DwHandleSubscribeMethod@@YAKPEAU_EXTENSION_CONTROL_BLOCK@@@Z; DwHandleSubscribeMethod(_EXTENSION_CONTROL_BLOCK *)
0x180006ebd  jmp     short loc_180006EDC
0x180006ebf  mov     rcx, [rdi+68h]
0x180006ec3  lea     rdx, aUnsubscribe; "UNSUBSCRIBE"
0x180006eca  call    cs:__imp__o__stricmp
0x180006ed0  test    eax, eax
0x180006ed2  jnz     short loc_180006EE5
0x180006ed4  mov     rcx, rdi; struct _EXTENSION_CONTROL_BLOCK *
0x180006ed7  call    ?DwHandleUnSubscribeMethod@@YAKPEAU_EXTENSION_CONTROL_BLOCK@@@Z; DwHandleUnSubscribeMethod(_EXTENSION_CONTROL_BLOCK *)
0x180006edc  mov     ebx, eax
0x180006ede  cmp     eax, 4
0x180006ee1  jnz     short loc_180006EFC
0x180006ee3  jmp     short loc_180006EF1
0x180006ee5  mov     dword ptr [rdi+10h], 190h
0x180006eec  mov     ebx, 4
0x180006ef1  mov     edx, [rdi+10h]; unsigned int
0x180006ef4  mov     rcx, rdi; struct _EXTENSION_CONTROL_BLOCK *
0x180006ef7  call    ?SendSimpleResponse@@YAXPEAU_EXTENSION_CONTROL_BLOCK@@K@Z; SendSimpleResponse(_EXTENSION_CONTROL_BLOCK *,ulong)
0x180006efc  call    cs:__imp_CoUninitialize
0x180006f02  cmp     ebx, 4
0x180006f05  jnz     short loc_180006F16
0x180006f07  jmp     short loc_180006F50
0x180006f09  mov     edx, 1F4h; unsigned int
0x180006f0e  mov     rcx, rdi; struct _EXTENSION_CONTROL_BLOCK *
0x180006f11  call    ?SendSimpleResponse@@YAXPEAU_EXTENSION_CONTROL_BLOCK@@K@Z; SendSimpleResponse(_EXTENSION_CONTROL_BLOCK *,ulong)
0x180006f16  mov     rcx, [rdi+8]
0x180006f1a  lea     r8, [rsp+38h+arg_0]
0x180006f1f  mov     rax, [rdi+0B8h]
0x180006f26  xor     r9d, r9d
0x180006f29  mov     edx, 3F0h
0x180006f2e  mov     [rsp+38h+arg_0], 0
0x180006f36  mov     [rsp+38h+var_18], 0
0x180006f3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f44  mov     eax, [rsp+38h+arg_0]
0x180006f48  neg     eax
0x180006f4a  sbb     ebx, ebx
0x180006f4c  neg     ebx
0x180006f4e  inc     ebx
0x180006f50  mov     eax, ebx
0x180006f52  mov     rbx, [rsp+38h+arg_8]
0x180006f57  add     rsp, 30h
0x180006f5b  pop     rdi
0x180006f5c  retn
```
