# xxxCreateDisconnectDesktop(HWINSTA__ *,tagWINDOWSTATION *)

- ea: `0x1401734b8`
- end: `0x140173774`
- name: `?xxxCreateDisconnectDesktop@@YAHPEAUHWINSTA__@@PEAUtagWINDOWSTATION@@@Z`
- size: `700`
- prototype: `int(HWINSTA, struct tagWINDOWSTATION *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140174168`

## callees

- `0x140059558`
- `0x1401734b8`
- `0x14017377c`
- `0x140173948`
- `0x140174168`

## import_xrefs

- `ntoskrnl!KeDetachProcess` at `0x1401736b6`
- `ntoskrnl!KeDetachProcess` at `0x1401736b6`
- `ntoskrnl!KeAttachProcess` at `0x140173651`
- `ntoskrnl!KeAttachProcess` at `0x140173651`
- `ntoskrnl!ExDesktopObjectType` at `0x1401735cc`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1401735fc`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1401735fc`
- `ntoskrnl!ObCloseHandle` at `0x140173751`
- `ntoskrnl!ObCloseHandle` at `0x140173751`
- `ntoskrnl!RtlInitUnicodeString` at `0x140173511`
- `ntoskrnl!RtlInitUnicodeString` at `0x140173511`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1401736a4`
- `ntoskrnl!ObOpenObjectByPointer` at `0x140173703`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1401736a4`
- `ntoskrnl!ObOpenObjectByPointer` at `0x140173703`
- `win32kbase!CreateEmptyRgnPublic` at `0x1401734ee`
- `win32kbase!CreateEmptyRgnPublic` at `0x1401734ee`
- `win32kbase!GreDeleteObject` at `0x14017357c`
- `win32kbase!GreDeleteObject` at `0x140173716`
- `win32kbase!GreDeleteObject` at `0x14017357c`
- `win32kbase!GreDeleteObject` at `0x140173716`
- `WIN32K!W32GetUserGdiSessionState` at `0x140173641`
- `WIN32K!W32GetUserGdiSessionState` at `0x140173641`
- `WIN32K!W32GetUserSessionState` at `0x140173593`
- `WIN32K!W32GetUserSessionState` at `0x1401735c0`
- `WIN32K!W32GetUserSessionState` at `0x14017361b`
- `WIN32K!W32GetUserSessionState` at `0x14017365d`
- `WIN32K!W32GetUserSessionState` at `0x140173670`
- `WIN32K!W32GetUserSessionState` at `0x1401736d0`
- `WIN32K!W32GetUserSessionState` at `0x140173727`
- `WIN32K!W32GetUserSessionState` at `0x140173593`
- `WIN32K!W32GetUserSessionState` at `0x1401735c0`
- `WIN32K!W32GetUserSessionState` at `0x14017361b`
- `WIN32K!W32GetUserSessionState` at `0x14017365d`
- `WIN32K!W32GetUserSessionState` at `0x140173670`
- `WIN32K!W32GetUserSessionState` at `0x1401736d0`
- `WIN32K!W32GetUserSessionState` at `0x140173727`

## pseudocode

```c
__int64 __fastcall xxxCreateDisconnectDesktop(HWINSTA a1, struct tagWINDOWSTATION *a2)
{
  __int64 EmptyRgnPublic; // rdi
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // r9
  __int64 UserSessionState; // rbx
  NTSTATUS v15; // eax
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // r9
  PVOID v19; // rcx
  __int64 v20; // rcx
  __int64 UserGdiSessionState; // rax
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // r8
  __int64 v25; // r9
  void **v26; // rdi
  __int64 v27; // rdx
  __int64 v28; // rcx
  __int64 v29; // r8
  __int64 v30; // r9
  __int64 v31; // rax
  __int64 v32; // rdx
  __int64 v33; // rcx
  NTSTATUS v34; // ebx
  __int64 v35; // r8
  __int64 v36; // r9
  __int64 v37; // rdx
  __int64 v38; // rcx
  __int64 v39; // r8
  __int64 v40; // r9
  __int64 v41; // rax
  __int64 v42; // rax
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-40h] BYREF
  __int128 v44; // [rsp+50h] [rbp-30h] BYREF
  __int128 v45; // [rsp+60h] [rbp-20h]
  __int128 v46; // [rsp+70h] [rbp-10h]
  HANDLE Handle; // [rsp+B0h] [rbp+30h] BYREF
  PVOID Object; // [rsp+B8h] [rbp+38h] BYREF

  Handle = 0;
  DestinationString = 0;
  v44 = 0;
  v45 = 0;
  v46 = 0;
  EmptyRgnPublic = CreateEmptyRgnPublic();
  if ( !EmptyRgnPublic )
    return 0;
  RtlInitUnicodeString(&DestinationString, L"Disconnect");
  *(_QWORD *)&v45 = &DestinationString;
  LODWORD(v44) = 48;
  *((_QWORD *)&v44 + 1) = a1;
  DWORD2(v45) = 192;
  v46 = 0;
  if ( (int)xxxCreateDesktopEx((__int64)&v44, 0, 0x2000000, 0, &Handle, 1) < 0 )
  {
    GreDeleteObject(EmptyRgnPublic);
    return 0;
  }
  if ( (int)SetDisconnectDesktopSecurity((HDESK)Handle) < 0
    || (UserSessionState = W32GetUserSessionState(v6, v5, v7, v8),
        Object = 0,
        v15 = ObReferenceObjectByHandle(Handle, 0, (POBJECT_TYPE)ExDesktopObjectType, 1, &Object, 0),
        v19 = Object,
        *(_QWORD *)(UserSessionState + 62752) = Object,
        v15 < 0) )
  {
    GreDeleteObject(EmptyRgnPublic);
    CloseDesktop(Handle);
    *(_QWORD *)(W32GetUserSessionState(v10, v9, v11, v12) + 62752) = 0;
    return 0;
  }
  v20 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(W32GetUserSessionState(v19, v16, v17, v18) + 62752) + 8LL) + 24LL);
  *(_QWORD *)(*(_QWORD *)(v20 + 40) + 168LL) = EmptyRgnPublic;
  UserGdiSessionState = W32GetUserGdiSessionState(v20);
  KeAttachProcess(*(PRKPROCESS *)(UserGdiSessionState + 40));
  v26 = (void **)(W32GetUserSessionState(v23, v22, v24, v25) + 68872);
  v31 = W32GetUserSessionState(v28, v27, v29, v30);
  v34 = ObOpenObjectByPointer(*(PVOID *)(v31 + 62752), 0x200u, 0, 0x1F0003u, 0, 0, v26);
  if ( v34 >= 0 )
  {
    v41 = W32GetUserSessionState(v33, v32, v35, v36);
    v34 = ObOpenObjectByPointer(a2, 0, 0, 0x1F0003u, 0, 0, (PHANDLE)(v41 + 68880));
  }
  KeDetachProcess();
  if ( v34 < 0 )
  {
    v42 = W32GetUserSessionState(v38, v37, v39, v40);
    tagWND::ClearClipRgnOrMaxClip(*(tagWND **)(*(_QWORD *)(*(_QWORD *)(v42 + 62752) + 8LL) + 24LL));
    if ( *v26 )
    {
      ObCloseHandle(*v26, 0);
      *v26 = 0;
    }
    CloseDesktop(Handle);
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x1401734b8  mov     [rsp-18h+arg_0], rbx
0x1401734bd  push    rbp
0x1401734be  push    rsi
0x1401734bf  push    rdi
0x1401734c0  mov     rbp, rsp
0x1401734c3  sub     rsp, 80h
0x1401734ca  xorps   xmm1, xmm1
0x1401734cd  mov     [rbp+Handle], 0
0x1401734d5  xorps   xmm0, xmm0
0x1401734d8  mov     rsi, rdx
0x1401734db  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1401734df  mov     rbx, rcx
0x1401734e2  movups  [rbp+var_30], xmm1
0x1401734e6  movups  [rbp+var_20], xmm1
0x1401734ea  movups  [rbp+var_10], xmm1
0x1401734ee  call    cs:__imp_CreateEmptyRgnPublic
0x1401734f5  nop     dword ptr [rax+rax+00h]
0x1401734fa  mov     rdi, rax
0x1401734fd  test    rax, rax
0x140173500  jz      loc_1401735AA
0x140173506  lea     rdx, aDisconnect; "Disconnect"
0x14017350d  lea     rcx, [rbp+DestinationString]; DestinationString
0x140173511  call    cs:__imp_RtlInitUnicodeString
0x140173518  nop     dword ptr [rax+rax+00h]
0x14017351d  lea     rax, [rbp+DestinationString]
0x140173521  mov     dword ptr [rsp+80h+HandleInformation], 1
0x140173529  mov     qword ptr [rbp+var_20], rax
0x14017352d  lea     rcx, [rbp+var_30]
0x140173531  lea     rax, [rbp+Handle]
0x140173535  mov     dword ptr [rbp+var_30], 30h ; '0'
0x14017353c  xorps   xmm0, xmm0
0x14017353f  mov     [rsp+80h+Object], rax
0x140173544  xor     r9d, r9d
0x140173547  mov     qword ptr [rbp+var_30+8], rbx
0x14017354b  xor     edx, edx
0x14017354d  mov     dword ptr [rbp+var_20+8], 0C0h
0x140173554  mov     r8d, 2000000h
0x14017355a  movdqu  [rbp+var_10], xmm0
0x14017355f  call    xxxCreateDesktopEx
0x140173564  test    eax, eax
0x140173566  js      loc_140173713
0x14017356c  mov     rcx, [rbp+Handle]; Handle
0x140173570  call    ?SetDisconnectDesktopSecurity@@YAJPEAUHDESK__@@@Z; SetDisconnectDesktopSecurity(HDESK__ *)
0x140173575  test    eax, eax
0x140173577  jns     short loc_1401735C0
0x140173579  mov     rcx, rdi
0x14017357c  call    cs:__imp_GreDeleteObject
0x140173583  nop     dword ptr [rax+rax+00h]
0x140173588  mov     rcx, [rbp+Handle]; Handle
0x14017358c  mov     dl, 1
0x14017358e  call    _CloseDesktop
0x140173593  call    cs:__imp_W32GetUserSessionState
0x14017359a  nop     dword ptr [rax+rax+00h]
0x14017359f  mov     qword ptr [rax+0F520h], 0
0x1401735aa  xor     eax, eax
0x1401735ac  mov     rbx, [rsp+80h+arg_0]
0x1401735b4  add     rsp, 80h
0x1401735bb  pop     rdi
0x1401735bc  pop     rsi
0x1401735bd  pop     rbp
0x1401735be  retn
0x1401735c0  call    cs:__imp_W32GetUserSessionState
0x1401735c7  nop     dword ptr [rax+rax+00h]
0x1401735cc  mov     r8, cs:ExDesktopObjectType
0x1401735d3  mov     r9b, 1; AccessMode
0x1401735d6  mov     rcx, [rbp+Handle]; Handle
0x1401735da  mov     rbx, rax
0x1401735dd  lea     rax, [rbp+arg_18]
0x1401735e1  mov     [rsp+80h+HandleInformation], 0; HandleInformation
0x1401735ea  xor     edx, edx; DesiredAccess
0x1401735ec  mov     [rbp+arg_18], 0
0x1401735f4  mov     r8, [r8]; ObjectType
0x1401735f7  mov     [rsp+80h+Object], rax; Object
0x1401735fc  call    cs:__imp_ObReferenceObjectByHandle
0x140173603  nop     dword ptr [rax+rax+00h]
0x140173608  mov     rcx, [rbp+arg_18]
0x14017360c  mov     [rbx+0F520h], rcx
0x140173613  test    eax, eax
0x140173615  js      loc_140173579
0x14017361b  call    cs:__imp_W32GetUserSessionState
0x140173622  nop     dword ptr [rax+rax+00h]
0x140173627  mov     rcx, [rax+0F520h]
0x14017362e  mov     rax, [rcx+8]
0x140173632  mov     rcx, [rax+18h]
0x140173636  mov     rax, [rcx+28h]
0x14017363a  mov     [rax+0A8h], rdi
0x140173641  call    cs:__imp_W32GetUserGdiSessionState
0x140173648  nop     dword ptr [rax+rax+00h]
0x14017364d  mov     rcx, [rax+28h]; Process
0x140173651  call    cs:__imp_KeAttachProcess
0x140173658  nop     dword ptr [rax+rax+00h]
0x14017365d  call    cs:__imp_W32GetUserSessionState
0x140173664  nop     dword ptr [rax+rax+00h]
0x140173669  lea     rdi, [rax+10D08h]
0x140173670  call    cs:__imp_W32GetUserSessionState
0x140173677  nop     dword ptr [rax+rax+00h]
0x14017367c  mov     [rsp+80h+var_50], rdi; Handle
0x140173681  mov     r9d, 1F0003h; DesiredAccess
0x140173687  mov     byte ptr [rsp+80h+HandleInformation], 0; AccessMode
0x14017368c  xor     r8d, r8d; PassedAccessState
0x14017368f  mov     edx, 200h; HandleAttributes
0x140173694  mov     [rsp+80h+Object], 0; ObjectType
0x14017369d  mov     rcx, [rax+0F520h]; Object
0x1401736a4  call    cs:__imp_ObOpenObjectByPointer
0x1401736ab  nop     dword ptr [rax+rax+00h]
0x1401736b0  mov     ebx, eax
0x1401736b2  test    eax, eax
0x1401736b4  jns     short loc_1401736D0
0x1401736b6  call    cs:__imp_KeDetachProcess
0x1401736bd  nop     dword ptr [rax+rax+00h]
0x1401736c2  test    ebx, ebx
0x1401736c4  js      short loc_140173727
0x1401736c6  mov     eax, 1
0x1401736cb  jmp     loc_1401735AC
0x1401736d0  call    cs:__imp_W32GetUserSessionState
0x1401736d7  nop     dword ptr [rax+rax+00h]
0x1401736dc  mov     r9d, 1F0003h; DesiredAccess
0x1401736e2  xor     r8d, r8d; PassedAccessState
0x1401736e5  add     rax, 10D10h
0x1401736eb  xor     edx, edx; HandleAttributes
0x1401736ed  mov     [rsp+80h+var_50], rax; Handle
0x1401736f2  mov     rcx, rsi; Object
0x1401736f5  mov     byte ptr [rsp+80h+HandleInformation], 0; AccessMode
0x1401736fa  mov     [rsp+80h+Object], 0; ObjectType
0x140173703  call    cs:__imp_ObOpenObjectByPointer
0x14017370a  nop     dword ptr [rax+rax+00h]
0x14017370f  mov     ebx, eax
0x140173711  jmp     short loc_1401736B6
0x140173713  mov     rcx, rdi
0x140173716  call    cs:__imp_GreDeleteObject
0x14017371d  nop     dword ptr [rax+rax+00h]
0x140173722  jmp     loc_1401735AA
0x140173727  call    cs:__imp_W32GetUserSessionState
0x14017372e  nop     dword ptr [rax+rax+00h]
0x140173733  mov     rcx, [rax+0F520h]
0x14017373a  mov     rcx, [rcx+8]
0x14017373e  mov     rcx, [rcx+18h]; this
0x140173742  call    ?ClearClipRgnOrMaxClip@tagWND@@QEAAXXZ; tagWND::ClearClipRgnOrMaxClip(void)
0x140173747  mov     rcx, [rdi]; Handle
0x14017374a  test    rcx, rcx
0x14017374d  jz      short loc_140173764
0x14017374f  xor     edx, edx; PreviousMode
0x140173751  call    cs:__imp_ObCloseHandle
0x140173758  nop     dword ptr [rax+rax+00h]
0x14017375d  mov     qword ptr [rdi], 0
0x140173764  mov     rcx, [rbp+Handle]; Handle
0x140173768  mov     dl, 1
0x14017376a  call    _CloseDesktop
0x14017376f  jmp     loc_1401735AA
```
