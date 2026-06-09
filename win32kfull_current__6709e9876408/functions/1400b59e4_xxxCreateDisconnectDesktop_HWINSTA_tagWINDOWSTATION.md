# xxxCreateDisconnectDesktop(HWINSTA__ *,tagWINDOWSTATION *)

- ea: `0x1400b59e4`
- end: `0x1400b5ca0`
- name: `?xxxCreateDisconnectDesktop@@YAHPEAUHWINSTA__@@PEAUtagWINDOWSTATION@@@Z`
- size: `700`
- prototype: `int(HWINSTA, struct tagWINDOWSTATION *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1400b66fc`

## callees

- `0x1400296e4`
- `0x1400b59e4`
- `0x1400b5ca8`
- `0x1400b5e78`
- `0x1400b66fc`

## import_xrefs

- `ntoskrnl!KeDetachProcess` at `0x1400b5be2`
- `ntoskrnl!KeDetachProcess` at `0x1400b5be2`
- `ntoskrnl!KeAttachProcess` at `0x1400b5b7d`
- `ntoskrnl!KeAttachProcess` at `0x1400b5b7d`
- `ntoskrnl!ExDesktopObjectType` at `0x1400b5af8`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400b5b28`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400b5b28`
- `ntoskrnl!ObCloseHandle` at `0x1400b5c7d`
- `ntoskrnl!ObCloseHandle` at `0x1400b5c7d`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400b5a3d`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400b5a3d`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400b5bd0`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400b5c2f`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400b5bd0`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400b5c2f`
- `win32kbase!CreateEmptyRgnPublic` at `0x1400b5a1a`
- `win32kbase!CreateEmptyRgnPublic` at `0x1400b5a1a`
- `win32kbase!GreDeleteObject` at `0x1400b5aa8`
- `win32kbase!GreDeleteObject` at `0x1400b5c42`
- `win32kbase!GreDeleteObject` at `0x1400b5aa8`
- `win32kbase!GreDeleteObject` at `0x1400b5c42`
- `WIN32K!W32GetUserGdiSessionState` at `0x1400b5b6d`
- `WIN32K!W32GetUserGdiSessionState` at `0x1400b5b6d`
- `WIN32K!W32GetUserSessionState` at `0x1400b5abf`
- `WIN32K!W32GetUserSessionState` at `0x1400b5aec`
- `WIN32K!W32GetUserSessionState` at `0x1400b5b47`
- `WIN32K!W32GetUserSessionState` at `0x1400b5b89`
- `WIN32K!W32GetUserSessionState` at `0x1400b5b9c`
- `WIN32K!W32GetUserSessionState` at `0x1400b5bfc`
- `WIN32K!W32GetUserSessionState` at `0x1400b5c53`
- `WIN32K!W32GetUserSessionState` at `0x1400b5abf`
- `WIN32K!W32GetUserSessionState` at `0x1400b5aec`
- `WIN32K!W32GetUserSessionState` at `0x1400b5b47`
- `WIN32K!W32GetUserSessionState` at `0x1400b5b89`
- `WIN32K!W32GetUserSessionState` at `0x1400b5b9c`
- `WIN32K!W32GetUserSessionState` at `0x1400b5bfc`
- `WIN32K!W32GetUserSessionState` at `0x1400b5c53`

## pseudocode

```c
__int64 __fastcall xxxCreateDisconnectDesktop(HWINSTA a1, struct tagWINDOWSTATION *a2)
{
  __int64 EmptyRgnPublic; // rdi
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 UserSessionState; // rbx
  NTSTATUS v9; // eax
  PVOID v10; // rcx
  __int64 v11; // rcx
  __int64 UserGdiSessionState; // rax
  __int64 v13; // rcx
  void **v14; // rdi
  __int64 v15; // rcx
  __int64 v16; // rax
  __int64 v17; // rcx
  NTSTATUS v18; // ebx
  __int64 v19; // rcx
  __int64 v20; // rax
  __int64 v21; // rax
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-40h] BYREF
  __int128 v23; // [rsp+50h] [rbp-30h] BYREF
  __int128 v24; // [rsp+60h] [rbp-20h]
  __int128 v25; // [rsp+70h] [rbp-10h]
  HANDLE Handle; // [rsp+B0h] [rbp+30h] BYREF
  PVOID Object; // [rsp+B8h] [rbp+38h] BYREF

  Handle = 0;
  DestinationString = 0;
  v23 = 0;
  v24 = 0;
  v25 = 0;
  EmptyRgnPublic = CreateEmptyRgnPublic();
  if ( !EmptyRgnPublic )
    return 0;
  RtlInitUnicodeString(&DestinationString, L"Disconnect");
  *(_QWORD *)&v24 = &DestinationString;
  LODWORD(v23) = 48;
  *((_QWORD *)&v23 + 1) = a1;
  DWORD2(v24) = 192;
  v25 = 0;
  if ( (int)xxxCreateDesktopEx((__int64)&v23, 0, 0x2000000, 0, &Handle, 1) < 0 )
  {
    GreDeleteObject(EmptyRgnPublic);
    return 0;
  }
  if ( (int)SetDisconnectDesktopSecurity((HDESK)Handle) < 0
    || (UserSessionState = W32GetUserSessionState(v5),
        Object = 0,
        v9 = ObReferenceObjectByHandle(Handle, 0, (POBJECT_TYPE)ExDesktopObjectType, 1, &Object, 0),
        v10 = Object,
        *(_QWORD *)(UserSessionState + 62752) = Object,
        v9 < 0) )
  {
    GreDeleteObject(EmptyRgnPublic);
    CloseDesktop(Handle);
    *(_QWORD *)(W32GetUserSessionState(v6) + 62752) = 0;
    return 0;
  }
  v11 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(W32GetUserSessionState(v10) + 62752) + 8LL) + 24LL);
  *(_QWORD *)(*(_QWORD *)(v11 + 40) + 168LL) = EmptyRgnPublic;
  UserGdiSessionState = W32GetUserGdiSessionState(v11);
  KeAttachProcess(*(PRKPROCESS *)(UserGdiSessionState + 40));
  v14 = (void **)(W32GetUserSessionState(v13) + 68872);
  v16 = W32GetUserSessionState(v15);
  v18 = ObOpenObjectByPointer(*(PVOID *)(v16 + 62752), 0x200u, 0, 0x1F0003u, 0, 0, v14);
  if ( v18 >= 0 )
  {
    v20 = W32GetUserSessionState(v17);
    v18 = ObOpenObjectByPointer(a2, 0, 0, 0x1F0003u, 0, 0, (PHANDLE)(v20 + 68880));
  }
  KeDetachProcess();
  if ( v18 < 0 )
  {
    v21 = W32GetUserSessionState(v19);
    tagWND::ClearClipRgnOrMaxClip(*(tagWND **)(*(_QWORD *)(*(_QWORD *)(v21 + 62752) + 8LL) + 24LL));
    if ( *v14 )
    {
      ObCloseHandle(*v14, 0);
      *v14 = 0;
    }
    CloseDesktop(Handle);
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x1400b59e4  mov     [rsp-18h+arg_0], rbx
0x1400b59e9  push    rbp
0x1400b59ea  push    rsi
0x1400b59eb  push    rdi
0x1400b59ec  mov     rbp, rsp
0x1400b59ef  sub     rsp, 80h
0x1400b59f6  xorps   xmm1, xmm1
0x1400b59f9  mov     [rbp+Handle], 0
0x1400b5a01  xorps   xmm0, xmm0
0x1400b5a04  mov     rsi, rdx
0x1400b5a07  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1400b5a0b  mov     rbx, rcx
0x1400b5a0e  movups  [rbp+var_30], xmm1
0x1400b5a12  movups  [rbp+var_20], xmm1
0x1400b5a16  movups  [rbp+var_10], xmm1
0x1400b5a1a  call    cs:__imp_CreateEmptyRgnPublic
0x1400b5a21  nop     dword ptr [rax+rax+00h]
0x1400b5a26  mov     rdi, rax
0x1400b5a29  test    rax, rax
0x1400b5a2c  jz      loc_1400B5AD6
0x1400b5a32  lea     rdx, aDisconnect; "Disconnect"
0x1400b5a39  lea     rcx, [rbp+DestinationString]; DestinationString
0x1400b5a3d  call    cs:__imp_RtlInitUnicodeString
0x1400b5a44  nop     dword ptr [rax+rax+00h]
0x1400b5a49  lea     rax, [rbp+DestinationString]
0x1400b5a4d  mov     dword ptr [rsp+80h+HandleInformation], 1
0x1400b5a55  mov     qword ptr [rbp+var_20], rax
0x1400b5a59  lea     rcx, [rbp+var_30]
0x1400b5a5d  lea     rax, [rbp+Handle]
0x1400b5a61  mov     dword ptr [rbp+var_30], 30h ; '0'
0x1400b5a68  xorps   xmm0, xmm0
0x1400b5a6b  mov     [rsp+80h+Object], rax
0x1400b5a70  xor     r9d, r9d
0x1400b5a73  mov     qword ptr [rbp+var_30+8], rbx
0x1400b5a77  xor     edx, edx
0x1400b5a79  mov     dword ptr [rbp+var_20+8], 0C0h
0x1400b5a80  mov     r8d, 2000000h
0x1400b5a86  movdqu  [rbp+var_10], xmm0
0x1400b5a8b  call    xxxCreateDesktopEx
0x1400b5a90  test    eax, eax
0x1400b5a92  js      loc_1400B5C3F
0x1400b5a98  mov     rcx, [rbp+Handle]; Handle
0x1400b5a9c  call    ?SetDisconnectDesktopSecurity@@YAJPEAUHDESK__@@@Z; SetDisconnectDesktopSecurity(HDESK__ *)
0x1400b5aa1  test    eax, eax
0x1400b5aa3  jns     short loc_1400B5AEC
0x1400b5aa5  mov     rcx, rdi
0x1400b5aa8  call    cs:__imp_GreDeleteObject
0x1400b5aaf  nop     dword ptr [rax+rax+00h]
0x1400b5ab4  mov     rcx, [rbp+Handle]; Handle
0x1400b5ab8  mov     dl, 1
0x1400b5aba  call    _CloseDesktop
0x1400b5abf  call    cs:__imp_W32GetUserSessionState
0x1400b5ac6  nop     dword ptr [rax+rax+00h]
0x1400b5acb  mov     qword ptr [rax+0F520h], 0
0x1400b5ad6  xor     eax, eax
0x1400b5ad8  mov     rbx, [rsp+80h+arg_0]
0x1400b5ae0  add     rsp, 80h
0x1400b5ae7  pop     rdi
0x1400b5ae8  pop     rsi
0x1400b5ae9  pop     rbp
0x1400b5aea  retn
0x1400b5aec  call    cs:__imp_W32GetUserSessionState
0x1400b5af3  nop     dword ptr [rax+rax+00h]
0x1400b5af8  mov     r8, cs:ExDesktopObjectType
0x1400b5aff  mov     r9b, 1; AccessMode
0x1400b5b02  mov     rcx, [rbp+Handle]; Handle
0x1400b5b06  mov     rbx, rax
0x1400b5b09  lea     rax, [rbp+arg_18]
0x1400b5b0d  mov     [rsp+80h+HandleInformation], 0; HandleInformation
0x1400b5b16  xor     edx, edx; DesiredAccess
0x1400b5b18  mov     [rbp+arg_18], 0
0x1400b5b20  mov     r8, [r8]; ObjectType
0x1400b5b23  mov     [rsp+80h+Object], rax; Object
0x1400b5b28  call    cs:__imp_ObReferenceObjectByHandle
0x1400b5b2f  nop     dword ptr [rax+rax+00h]
0x1400b5b34  mov     rcx, [rbp+arg_18]
0x1400b5b38  mov     [rbx+0F520h], rcx
0x1400b5b3f  test    eax, eax
0x1400b5b41  js      loc_1400B5AA5
0x1400b5b47  call    cs:__imp_W32GetUserSessionState
0x1400b5b4e  nop     dword ptr [rax+rax+00h]
0x1400b5b53  mov     rcx, [rax+0F520h]
0x1400b5b5a  mov     rax, [rcx+8]
0x1400b5b5e  mov     rcx, [rax+18h]
0x1400b5b62  mov     rax, [rcx+28h]
0x1400b5b66  mov     [rax+0A8h], rdi
0x1400b5b6d  call    cs:__imp_W32GetUserGdiSessionState
0x1400b5b74  nop     dword ptr [rax+rax+00h]
0x1400b5b79  mov     rcx, [rax+28h]; Process
0x1400b5b7d  call    cs:__imp_KeAttachProcess
0x1400b5b84  nop     dword ptr [rax+rax+00h]
0x1400b5b89  call    cs:__imp_W32GetUserSessionState
0x1400b5b90  nop     dword ptr [rax+rax+00h]
0x1400b5b95  lea     rdi, [rax+10D08h]
0x1400b5b9c  call    cs:__imp_W32GetUserSessionState
0x1400b5ba3  nop     dword ptr [rax+rax+00h]
0x1400b5ba8  mov     [rsp+80h+var_50], rdi; Handle
0x1400b5bad  mov     r9d, 1F0003h; DesiredAccess
0x1400b5bb3  mov     byte ptr [rsp+80h+HandleInformation], 0; AccessMode
0x1400b5bb8  xor     r8d, r8d; PassedAccessState
0x1400b5bbb  mov     edx, 200h; HandleAttributes
0x1400b5bc0  mov     [rsp+80h+Object], 0; ObjectType
0x1400b5bc9  mov     rcx, [rax+0F520h]; Object
0x1400b5bd0  call    cs:__imp_ObOpenObjectByPointer
0x1400b5bd7  nop     dword ptr [rax+rax+00h]
0x1400b5bdc  mov     ebx, eax
0x1400b5bde  test    eax, eax
0x1400b5be0  jns     short loc_1400B5BFC
0x1400b5be2  call    cs:__imp_KeDetachProcess
0x1400b5be9  nop     dword ptr [rax+rax+00h]
0x1400b5bee  test    ebx, ebx
0x1400b5bf0  js      short loc_1400B5C53
0x1400b5bf2  mov     eax, 1
0x1400b5bf7  jmp     loc_1400B5AD8
0x1400b5bfc  call    cs:__imp_W32GetUserSessionState
0x1400b5c03  nop     dword ptr [rax+rax+00h]
0x1400b5c08  mov     r9d, 1F0003h; DesiredAccess
0x1400b5c0e  xor     r8d, r8d; PassedAccessState
0x1400b5c11  add     rax, 10D10h
0x1400b5c17  xor     edx, edx; HandleAttributes
0x1400b5c19  mov     [rsp+80h+var_50], rax; Handle
0x1400b5c1e  mov     rcx, rsi; Object
0x1400b5c21  mov     byte ptr [rsp+80h+HandleInformation], 0; AccessMode
0x1400b5c26  mov     [rsp+80h+Object], 0; ObjectType
0x1400b5c2f  call    cs:__imp_ObOpenObjectByPointer
0x1400b5c36  nop     dword ptr [rax+rax+00h]
0x1400b5c3b  mov     ebx, eax
0x1400b5c3d  jmp     short loc_1400B5BE2
0x1400b5c3f  mov     rcx, rdi
0x1400b5c42  call    cs:__imp_GreDeleteObject
0x1400b5c49  nop     dword ptr [rax+rax+00h]
0x1400b5c4e  jmp     loc_1400B5AD6
0x1400b5c53  call    cs:__imp_W32GetUserSessionState
0x1400b5c5a  nop     dword ptr [rax+rax+00h]
0x1400b5c5f  mov     rcx, [rax+0F520h]
0x1400b5c66  mov     rcx, [rcx+8]
0x1400b5c6a  mov     rcx, [rcx+18h]; this
0x1400b5c6e  call    ?ClearClipRgnOrMaxClip@tagWND@@QEAAXXZ; tagWND::ClearClipRgnOrMaxClip(void)
0x1400b5c73  mov     rcx, [rdi]; Handle
0x1400b5c76  test    rcx, rcx
0x1400b5c79  jz      short loc_1400B5C90
0x1400b5c7b  xor     edx, edx; PreviousMode
0x1400b5c7d  call    cs:__imp_ObCloseHandle
0x1400b5c84  nop     dword ptr [rax+rax+00h]
0x1400b5c89  mov     qword ptr [rdi], 0
0x1400b5c90  mov     rcx, [rbp+Handle]; Handle
0x1400b5c94  mov     dl, 1
0x1400b5c96  call    _CloseDesktop
0x1400b5c9b  jmp     loc_1400B5AD6
```
