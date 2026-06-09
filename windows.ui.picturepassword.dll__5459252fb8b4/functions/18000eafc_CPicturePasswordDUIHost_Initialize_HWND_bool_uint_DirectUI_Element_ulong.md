# CPicturePasswordDUIHost::Initialize(HWND__ *,bool,uint,DirectUI::Element *,ulong *)

- ea: `0x18000eafc`
- end: `0x18000ebbf`
- name: `?Initialize@CPicturePasswordDUIHost@@QEAAJPEAUHWND__@@_NIPEAVElement@DirectUI@@PEAK@Z`
- size: `195`
- prototype: `int __fastcall(CPicturePasswordDUIHost *this, HWND, __int64, __int64, struct DirectUI::Element *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000e0dc`

## callees

- `0x18000eafc`
- `0x180018884`
- `0x180019d44`

## import_xrefs

- `DUI70!?Initialize@TouchHWNDElement@DirectUI@@QEAAJPEAUHWND__@@_NIPEAVElement@2@PEAK@Z` at `0x18000eb82`
- `DUI70!?Initialize@TouchHWNDElement@DirectUI@@QEAAJPEAUHWND__@@_NIPEAVElement@2@PEAK@Z` at `0x18000eb82`
- `DUI70!?CreateInstance@CSafeElementProxy@@SAJPEAVElement@DirectUI@@PEAPEAV1@@Z` at `0x18000eba3`
- `DUI70!?CreateInstance@CSafeElementProxy@@SAJPEAVElement@DirectUI@@PEAPEAV1@@Z` at `0x18000eba3`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SetPropW` at `0x18000eb33`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SetPropW` at `0x18000eb33`

## string_xrefs

- `0x18000eb29`: `ImmersiveComponentOwnedWindow`

## pseudocode

```c
int __fastcall CPicturePasswordDUIHost::Initialize(
        CPicturePasswordDUIHost *this,
        HWND a2,
        __int64 a3,
        __int64 a4,
        struct DirectUI::Element *a5,
        unsigned int *a6)
{
  int result; // eax

  *a6 = 0;
  *((_QWORD *)this + 109) = a2;
  if ( !SetPropW(a2, L"ImmersiveComponentOwnedWindow", HANDLE_FLAG_INHERIT) )
    ResultFromLastError();
  result = CPrivateNotificationWindow::CreateInstance(
             (struct CPrivateNotificationWindowSink *)(((unsigned __int64)this + 440) & -(__int64)(this != 0)),
             (struct CPrivateNotificationWindow **)this + 91);
  if ( result >= 0 )
  {
    result = DirectUI::TouchHWNDElement::Initialize(this, a2, 1, 0x1Cu, 0, a6);
    if ( result >= 0 )
    {
      result = *((_DWORD *)this + 106);
      if ( result == -2147024875 )
      {
        result = CSafeElementProxy::CreateInstance(this, (struct CSafeElementProxy **)this + 54);
        *((_DWORD *)this + 106) = result;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000eafc  mov     [rsp+arg_0], rbx
0x18000eb01  mov     [rsp+arg_8], rsi
0x18000eb06  push    rdi
0x18000eb07  sub     rsp, 30h
0x18000eb0b  mov     rsi, [rsp+38h+arg_28]
0x18000eb10  mov     rdi, rdx
0x18000eb13  mov     rbx, rcx
0x18000eb16  mov     r8d, 1; hData
0x18000eb1c  mov     dword ptr [rsi], 0
0x18000eb22  mov     [rcx+368h], rdx
0x18000eb29  lea     rdx, String; "ImmersiveComponentOwnedWindow"
0x18000eb30  mov     rcx, rdi; hWnd
0x18000eb33  call    cs:__imp_SetPropW
0x18000eb39  test    eax, eax
0x18000eb3b  jnz     short loc_18000EB42
0x18000eb3d  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18000eb42  lea     r9, [rbx+1B8h]
0x18000eb49  mov     rax, rbx
0x18000eb4c  neg     rax
0x18000eb4f  lea     rdx, [rbx+2D8h]; struct CPrivateNotificationWindow **
0x18000eb56  sbb     rcx, rcx
0x18000eb59  and     rcx, r9; struct CPrivateNotificationWindowSink *
0x18000eb5c  call    ?CreateInstance@CPrivateNotificationWindow@@SAJPEAVCPrivateNotificationWindowSink@@PEAPEAV1@@Z; CPrivateNotificationWindow::CreateInstance(CPrivateNotificationWindowSink *,CPrivateNotificationWindow * *)
0x18000eb61  test    eax, eax
0x18000eb63  js      short loc_18000EBAF
0x18000eb65  mov     [rsp+38h+var_10], rsi
0x18000eb6a  mov     r9d, 1Ch
0x18000eb70  mov     r8b, 1
0x18000eb73  mov     [rsp+38h+var_18], 0
0x18000eb7c  mov     rdx, rdi
0x18000eb7f  mov     rcx, rbx
0x18000eb82  call    cs:__imp_?Initialize@TouchHWNDElement@DirectUI@@QEAAJPEAUHWND__@@_NIPEAVElement@2@PEAK@Z; DirectUI::TouchHWNDElement::Initialize(HWND__ *,bool,uint,DirectUI::Element *,ulong *)
0x18000eb88  test    eax, eax
0x18000eb8a  js      short loc_18000EBAF
0x18000eb8c  mov     eax, [rbx+1A8h]
0x18000eb92  cmp     eax, 80070015h
0x18000eb97  jnz     short loc_18000EBAF
0x18000eb99  lea     rdx, [rbx+1B0h]
0x18000eba0  mov     rcx, rbx
0x18000eba3  call    cs:__imp_?CreateInstance@CSafeElementProxy@@SAJPEAVElement@DirectUI@@PEAPEAV1@@Z; CSafeElementProxy::CreateInstance(DirectUI::Element *,CSafeElementProxy * *)
0x18000eba9  mov     [rbx+1A8h], eax
0x18000ebaf  mov     rbx, [rsp+38h+arg_0]
0x18000ebb4  mov     rsi, [rsp+38h+arg_8]
0x18000ebb9  add     rsp, 30h
0x18000ebbd  pop     rdi
0x18000ebbe  retn
```
