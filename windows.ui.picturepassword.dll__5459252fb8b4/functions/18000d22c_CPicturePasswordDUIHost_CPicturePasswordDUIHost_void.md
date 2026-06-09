# CPicturePasswordDUIHost::~CPicturePasswordDUIHost(void)

- ea: `0x18000d22c`
- end: `0x18000d36a`
- name: `??1CPicturePasswordDUIHost@@UEAA@XZ`
- size: `318`
- prototype: `void __fastcall(CPicturePasswordDUIHost *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18000d980`

## callees

- `0x180002bb0`
- `0x1800043a4`
- `0x18000d058`
- `0x18000d0f0`
- `0x18000d22c`
- `0x180013f60`
- `0x180018910`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d28c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d28c`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x18000d2a5`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x18000d2a5`
- `ext-ms-win-ntuser-rotationmanager-l1-1-0!SetDisplayAutoRotationPreferences` at `0x18000d318`
- `ext-ms-win-ntuser-rotationmanager-l1-1-0!SetDisplayAutoRotationPreferences` at `0x18000d318`

## pseudocode

```c
void __fastcall CPicturePasswordDUIHost::~CPicturePasswordDUIHost(CPicturePasswordDUIHost *this)
{
  __int64 v1; // rdi
  _BYTE *v3; // rax
  __int64 i; // rcx
  DirectUI::DUIXmlParser *v5; // rcx
  CPrivateNotificationWindow *v6; // rcx
  CPrivateNotificationWindow *v7; // rcx
  CPrivateNotificationWindow *v8; // rcx
  CPrivateNotificationWindow *v9; // rcx

  v1 = 0;
  *(_QWORD *)this = &CPicturePasswordDUIHost::`vftable'{for `CElementWithProxy<DirectUI::TouchHWNDElement>'};
  *((_QWORD *)this + 55) = &CPicturePasswordDUIHost::`vftable'{for `CPrivateNotificationWindowSink'};
  *((_QWORD *)this + 56) = &CPicturePasswordDUIHost::`vftable'{for `CElementListener'};
  v3 = (_BYTE *)*((_QWORD *)this + 57);
  if ( v3 )
  {
    for ( i = *((_QWORD *)this + 58); i; --i )
      *v3++ = 0;
    CoTaskMemFree(*((LPVOID *)this + 57));
    *((_QWORD *)this + 57) = 0;
  }
  v5 = (DirectUI::DUIXmlParser *)*((_QWORD *)this + 89);
  if ( v5 )
  {
    DirectUI::DUIXmlParser::Destroy(v5);
    *((_QWORD *)this + 89) = 0;
  }
  v6 = (CPrivateNotificationWindow *)*((_QWORD *)this + 91);
  if ( v6 )
  {
    CPrivateNotificationWindow::DisconnectAndRelease(v6);
    *((_QWORD *)this + 91) = 0;
  }
  v7 = (CPrivateNotificationWindow *)*((_QWORD *)this + 114);
  if ( v7 )
  {
    CPrivateNotificationWindow::DisconnectAndRelease(v7);
    *((_QWORD *)this + 114) = 0;
  }
  v8 = (CPrivateNotificationWindow *)*((_QWORD *)this + 115);
  if ( v8 )
  {
    CPrivateNotificationWindow::DisconnectAndRelease(v8);
    *((_QWORD *)this + 115) = 0;
  }
  v9 = (CPrivateNotificationWindow *)*((_QWORD *)this + 116);
  if ( v9 )
  {
    CPrivateNotificationWindow::DisconnectAndRelease(v9);
    *((_QWORD *)this + 116) = 0;
  }
  SetDisplayAutoRotationPreferences(*((ORIENTATION_PREFERENCE *)this + 234));
  do
    operator delete(*((void **)this + v1++ + 123));
  while ( v1 != 8 );
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 736);
  CGestureSignatureArray::~CGestureSignatureArray((CPicturePasswordDUIHost *)((char *)this + 672));
  CPicturePasswordGestureHelper::~CPicturePasswordGestureHelper((CPicturePasswordDUIHost *)((char *)this + 472));
  CElementWithProxy<DirectUI::TouchHWNDElement>::~CElementWithProxy<DirectUI::TouchHWNDElement>(this);
}

```

## disassembly

```asm
0x18000d22c  mov     [rsp+arg_0], rbx
0x18000d231  push    rdi
0x18000d232  sub     rsp, 20h
0x18000d236  lea     rax, ??_7CPicturePasswordDUIHost@@6B?$CElementWithProxy@VTouchHWNDElement@DirectUI@@@@@; const CPicturePasswordDUIHost::`vftable'{for `CElementWithProxy<DirectUI::TouchHWNDElement>'}
0x18000d23d  xor     edi, edi
0x18000d23f  mov     [rcx], rax
0x18000d242  mov     rbx, rcx
0x18000d245  lea     rax, ??_7CPicturePasswordDUIHost@@6BCPrivateNotificationWindowSink@@@; const CPicturePasswordDUIHost::`vftable'{for `CPrivateNotificationWindowSink'}
0x18000d24c  mov     [rcx+1B8h], rax
0x18000d253  lea     rax, ??_7CPicturePasswordDUIHost@@6BCElementListener@@@; const CPicturePasswordDUIHost::`vftable'{for `CElementListener'}
0x18000d25a  mov     [rcx+1C0h], rax
0x18000d261  mov     rax, [rcx+1C8h]
0x18000d268  test    rax, rax
0x18000d26b  jz      short loc_18000D299
0x18000d26d  mov     rcx, [rcx+1D0h]
0x18000d274  test    rcx, rcx
0x18000d277  jz      short loc_18000D285
0x18000d279  mov     [rax], dil
0x18000d27c  inc     rax
0x18000d27f  sub     rcx, 1
0x18000d283  jnz     short loc_18000D279
0x18000d285  mov     rcx, [rbx+1C8h]; pv
0x18000d28c  call    cs:__imp_CoTaskMemFree
0x18000d292  mov     [rbx+1C8h], rdi
0x18000d299  mov     rcx, [rbx+2C8h]
0x18000d2a0  test    rcx, rcx
0x18000d2a3  jz      short loc_18000D2B2
0x18000d2a5  call    cs:__imp_?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ; DirectUI::DUIXmlParser::Destroy(void)
0x18000d2ab  mov     [rbx+2C8h], rdi
0x18000d2b2  mov     rcx, [rbx+2D8h]; this
0x18000d2b9  test    rcx, rcx
0x18000d2bc  jz      short loc_18000D2CA
0x18000d2be  call    ?DisconnectAndRelease@CPrivateNotificationWindow@@QEAAXXZ; CPrivateNotificationWindow::DisconnectAndRelease(void)
0x18000d2c3  mov     [rbx+2D8h], rdi
0x18000d2ca  mov     rcx, [rbx+390h]; this
0x18000d2d1  test    rcx, rcx
0x18000d2d4  jz      short loc_18000D2E2
0x18000d2d6  call    ?DisconnectAndRelease@CPrivateNotificationWindow@@QEAAXXZ; CPrivateNotificationWindow::DisconnectAndRelease(void)
0x18000d2db  mov     [rbx+390h], rdi
0x18000d2e2  mov     rcx, [rbx+398h]; this
0x18000d2e9  test    rcx, rcx
0x18000d2ec  jz      short loc_18000D2FA
0x18000d2ee  call    ?DisconnectAndRelease@CPrivateNotificationWindow@@QEAAXXZ; CPrivateNotificationWindow::DisconnectAndRelease(void)
0x18000d2f3  mov     [rbx+398h], rdi
0x18000d2fa  mov     rcx, [rbx+3A0h]; this
0x18000d301  test    rcx, rcx
0x18000d304  jz      short loc_18000D312
0x18000d306  call    ?DisconnectAndRelease@CPrivateNotificationWindow@@QEAAXXZ; CPrivateNotificationWindow::DisconnectAndRelease(void)
0x18000d30b  mov     [rbx+3A0h], rdi
0x18000d312  mov     ecx, [rbx+3A8h]; orientation
0x18000d318  call    cs:__imp_SetDisplayAutoRotationPreferences
0x18000d31e  mov     rcx, [rbx+rdi*8+3D8h]; Block
0x18000d326  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000d32b  inc     rdi
0x18000d32e  cmp     rdi, 8
0x18000d332  jnz     short loc_18000D31E
0x18000d334  lea     rcx, [rbx+2E0h]
0x18000d33b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000d340  lea     rcx, [rbx+2A0h]; this
0x18000d347  call    ??1CGestureSignatureArray@@UEAA@XZ; CGestureSignatureArray::~CGestureSignatureArray(void)
0x18000d34c  lea     rcx, [rbx+1D8h]; this
0x18000d353  call    ??1CPicturePasswordGestureHelper@@UEAA@XZ; CPicturePasswordGestureHelper::~CPicturePasswordGestureHelper(void)
0x18000d358  mov     rcx, rbx
0x18000d35b  mov     rbx, [rsp+28h+arg_0]
0x18000d360  add     rsp, 20h
0x18000d364  pop     rdi
0x18000d365  jmp     ??1?$CElementWithProxy@VTouchHWNDElement@DirectUI@@@@UEAA@XZ; CElementWithProxy<DirectUI::TouchHWNDElement>::~CElementWithProxy<DirectUI::TouchHWNDElement>(void)
```
