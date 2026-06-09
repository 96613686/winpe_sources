# ClientEndpoint::~ClientEndpoint(void)

- ea: `0x18002d158`
- end: `0x18002d219`
- name: `??1ClientEndpoint@@QEAA@XZ`
- size: `193`
- prototype: `void __fastcall(HSTRING *this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002d9b0`

## callees

- `0x180005f50`
- `0x18000fe24`
- `0x180010278`
- `0x18002d13c`
- `0x18002d158`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002d168`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002d1d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002d1e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002d1f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002d168`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002d1d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002d1e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002d1f5`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
void __fastcall ClientEndpoint::~ClientEndpoint(HSTRING *this)
{
  std::_Ref_count_base *v2; // rcx
  std::_Ref_count_base *v3; // rcx
  std::_Ref_count_base *v4; // rcx

  WindowsDeleteString(this[21]);
  this[21] = 0;
  std::unique_ptr<RefreshPolicy>::~unique_ptr<RefreshPolicy>(this + 18);
  v2 = (std::_Ref_count_base *)this[17];
  if ( v2 )
    std::_Ref_count_base::_Decref(v2);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(this + 15);
  v3 = (std::_Ref_count_base *)this[14];
  if ( v3 )
    std::_Ref_count_base::_Decref(v3);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(this + 12);
  v4 = (std::_Ref_count_base *)this[11];
  if ( v4 )
    std::_Ref_count_base::_Decref(v4);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(this + 9);
  WindowsDeleteString(this[7]);
  this[7] = 0;
  WindowsDeleteString(this[6]);
  this[6] = 0;
  WindowsDeleteString(this[5]);
  this[5] = 0;
  std::wstring::_Tidy_deallocate(this + 1);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(this);
}

```

## disassembly

```asm
0x18002d158  push    rbx
0x18002d15a  sub     rsp, 20h
0x18002d15e  mov     rbx, rcx
0x18002d161  mov     rcx, [rcx+0A8h]; string
0x18002d168  call    cs:__imp_WindowsDeleteString
0x18002d16e  lea     rcx, [rbx+90h]
0x18002d175  mov     qword ptr [rbx+0A8h], 0
0x18002d180  call    ??1?$unique_ptr@VRefreshPolicy@@U?$default_delete@VRefreshPolicy@@@std@@@std@@QEAA@XZ; std::unique_ptr<RefreshPolicy>::~unique_ptr<RefreshPolicy>(void)
0x18002d185  mov     rcx, [rbx+88h]; this
0x18002d18c  test    rcx, rcx
0x18002d18f  jz      short loc_18002D196
0x18002d191  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002d196  lea     rcx, [rbx+78h]
0x18002d19a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002d19f  mov     rcx, [rbx+70h]; this
0x18002d1a3  test    rcx, rcx
0x18002d1a6  jz      short loc_18002D1AD
0x18002d1a8  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002d1ad  lea     rcx, [rbx+60h]
0x18002d1b1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002d1b6  mov     rcx, [rbx+58h]; this
0x18002d1ba  test    rcx, rcx
0x18002d1bd  jz      short loc_18002D1C4
0x18002d1bf  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002d1c4  lea     rcx, [rbx+48h]
0x18002d1c8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002d1cd  mov     rcx, [rbx+38h]; string
0x18002d1d1  call    cs:__imp_WindowsDeleteString
0x18002d1d7  mov     qword ptr [rbx+38h], 0
0x18002d1df  mov     rcx, [rbx+30h]; string
0x18002d1e3  call    cs:__imp_WindowsDeleteString
0x18002d1e9  mov     qword ptr [rbx+30h], 0
0x18002d1f1  mov     rcx, [rbx+28h]; string
0x18002d1f5  call    cs:__imp_WindowsDeleteString
0x18002d1fb  lea     rcx, [rbx+8]
0x18002d1ff  mov     qword ptr [rbx+28h], 0
0x18002d207  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002d20c  mov     rcx, rbx
0x18002d20f  add     rsp, 20h
0x18002d213  pop     rbx
0x18002d214  jmp     ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
```
