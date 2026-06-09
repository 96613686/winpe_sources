# winrt::WindowsUdk::Media::Devices::implementation::VirtualAudioStreamOutputImpl::WriteAsync$_ResumeCoro$1

- ea: `0x1802e7000`
- end: `0x1802e71a8`
- name: `winrt::WindowsUdk::Media::Devices::implementation::VirtualAudioStreamOutputImpl::WriteAsync$_ResumeCoro$1`
- size: `424`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1802e720c`

## callees

- `0x18003b61c`
- `0x180071388`
- `0x1800f5e5c`
- `0x1800f88a0`
- `0x18015cfa0`
- `0x18028b43c`
- `0x1802e6870`
- `0x1802e7000`
- `0x1802e76ec`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x1802e7109`
- `msvcp_win!_Mtx_unlock` at `0x1802e7128`
- `msvcp_win!_Mtx_unlock` at `0x1802e7109`
- `msvcp_win!_Mtx_unlock` at `0x1802e7128`
- `Apx01000!imp_ApxStreamWriteData` at `0x1802e70bf`
- `Apx01000!imp_ApxStreamWriteData` at `0x1802e70bf`

## string_xrefs

- `0x1802e70d9`: `shellcommon\undockeddevkit\libs\windowsudk.media.devices\virtualaudiostream.cpp`
- `0x1802e70ca`: `ApxStreamWriteData failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall winrt::WindowsUdk::Media::Devices::implementation::VirtualAudioStreamOutputImpl::WriteAsync__ResumeCoro_1(
        __int64 a1)
{
  _WORD *v2; // r14
  __int64 v3; // rsi
  struct _Mtx_internal_imp_t *v4; // r15
  unsigned int v5; // r12d
  __int64 v6; // rax
  unsigned int v7; // eax
  __int64 v8; // rsi
  const char *v9; // [rsp+28h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v2 = (_WORD *)(a1 + 8);
  switch ( *(_WORD *)(a1 + 8) )
  {
    case 0xFFFF:
    case 1:
    case 3:
      goto LABEL_7;
    case 2:
      v3 = *(_QWORD *)(a1 + 56);
      v4 = (struct _Mtx_internal_imp_t *)(v3 + 48);
      *(_QWORD *)(a1 + 16) = v3 + 48;
      std::_Mutex_base::lock((std::_Mutex_base *)(v3 + 48));
      if ( *(_QWORD *)(v3 + 32) && *(_BYTE *)(v3 + 128) )
      {
        v5 = (unsigned int)winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::Windows::UI::Internal::Text::Core::CoreTextKeyFilter>,winrt::Windows::UI::Internal::Text::Core::CoreTextKeyFilter>::Size(*(_QWORD *)(a1 + 64))
           / (*(unsigned __int8 *)(v3 + 41) >> 3)
           / *(unsigned __int8 *)(v3 + 40);
        v6 = winrt::impl::consume_Windows_Storage_Streams_IBuffer<winrt::Windows::Storage::Streams::IBuffer>::data(*(_QWORD *)(a1 + 64));
        v7 = imp_ApxStreamWriteData(0, *(_QWORD *)(v3 + 32), v6, v5, 0);
        wil::details::in1diag3::Throw_IfFailedMsg(
          retaddr,
          (void *)0x120,
          (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.media.devices\\virtualaudiostream.cpp",
          (const char *)v7,
          (int)"ApxStreamWriteData failed",
          v9);
        v8 = a1 - 128;
        *(_DWORD *)(a1 + 28) = winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::Windows::UI::Internal::Text::Core::CoreTextKeyFilter>,winrt::Windows::UI::Internal::Text::Core::CoreTextKeyFilter>::Size(*(_QWORD *)(a1 + 64));
        std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<unsigned int,unsigned int>,winrt::WindowsUdk::Media::Devices::implementation::VirtualAudioStreamOutputImpl *,winrt::Windows::Storage::Streams::IBuffer const &>::promise_type::return_value(a1 - 128);
        _Mtx_unlock(v4);
      }
      else
      {
        v8 = a1 - 128;
        *(_DWORD *)(a1 + 24) = 0;
        std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<unsigned int,unsigned int>,winrt::WindowsUdk::Media::Devices::implementation::VirtualAudioStreamOutputImpl *,winrt::Windows::Storage::Streams::IBuffer const &>::promise_type::return_value(a1 - 128);
        _Mtx_unlock(v4);
      }
      *(_QWORD *)(a1 + 32) = v8;
      *v2 = 0;
      if ( !(unsigned __int8)winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Foundation::Collections::IVectorView<winrt::WindowsUdk::UI::MenuItem>>,winrt::Windows::Storage::IStorageItem,winrt::Windows::System::User,winrt::WindowsUdk::UI::MenuItemGetOptions>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Foundation::Collections::IVectorView<winrt::WindowsUdk::UI::MenuItem>>,void>::final_suspend_awaiter::await_suspend() )
      {
LABEL_7:
        std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<unsigned int,unsigned int>,winrt::WindowsUdk::Media::Devices::implementation::VirtualAudioStreamOutputImpl *,winrt::Windows::Storage::Streams::IBuffer const &>::promise_type::~promise_type(a1 - 128);
        if ( *(_WORD *)(a1 + 10) )
          operator delete((void *)(a1 - 128), (const struct std::nothrow_t *)0xD0);
      }
      break;
    default:
      __debugbreak();
      break;
  }
}

```

## disassembly

```asm
0x1802e7000  mov     [rsp+arg_10], rbx
0x1802e7005  mov     [rsp+arg_0], rcx
0x1802e700a  push    rsi
0x1802e700b  push    rdi
0x1802e700c  push    r12
0x1802e700e  push    r14
0x1802e7010  push    r15
0x1802e7012  sub     rsp, 40h
0x1802e7016  mov     rbx, [rsp+68h+arg_0]
0x1802e701b  lea     r14, [rbx+8]
0x1802e701f  mov     [rsp+68h+arg_8], r14
0x1802e7024  movzx   eax, word ptr [r14]
0x1802e7028  mov     [rsp+68h+var_38], ax
0x1802e702d  inc     ax; switch 5 cases
0x1802e7030  cmp     ax, 4
0x1802e7034  ja      def_1802E704F; jumptable 00000001802E704F default case, case 0
0x1802e703a  movsx   rax, ax
0x1802e703e  lea     rdx, __ImageBase
0x1802e7045  mov     ecx, ds:(jpt_1802E704F - 180000000h)[rdx+rax*4]
0x1802e704c  add     rcx, rdx
0x1802e704f  jmp     rcx; switch jump
0x1802e7051  xor     edi, edi; jumptable 00000001802E704F case 3
0x1802e7053  jmp     loc_1802E715B
0x1802e7058  mov     rsi, [r14+30h]; jumptable 00000001802E704F case 2
0x1802e705c  lea     r15, [rsi+30h]
0x1802e7060  mov     [rbx+10h], r15
0x1802e7064  mov     rcx, r15; this
0x1802e7067  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x1802e706c  nop
0x1802e706d  xor     edi, edi
0x1802e706f  cmp     [rsi+20h], rdi
0x1802e7073  jz      loc_1802E7112
0x1802e7079  cmp     [rsi+80h], dil
0x1802e7080  jz      loc_1802E7112
0x1802e7086  mov     rcx, [rbx+40h]
0x1802e708a  call    ?Size@?$consume_Windows_Foundation_Collections_IVector@U?$IVector@UCoreTextKeyFilter@Core@Text@Internal@UI@Windows@winrt@@@Collections@Foundation@Windows@winrt@@UCoreTextKeyFilter@Core@Text@Internal@UI@45@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::Windows::UI::Internal::Text::Core::CoreTextKeyFilter>,winrt::Windows::UI::Internal::Text::Core::CoreTextKeyFilter>::Size(void)
0x1802e708f  movzx   ecx, byte ptr [rsi+29h]
0x1802e7093  shr     ecx, 3
0x1802e7096  xor     edx, edx
0x1802e7098  div     ecx
0x1802e709a  movzx   ecx, byte ptr [rsi+28h]
0x1802e709e  xor     edx, edx
0x1802e70a0  div     ecx
0x1802e70a2  mov     r12d, eax
0x1802e70a5  mov     rcx, [rbx+40h]
0x1802e70a9  call    ?data@?$consume_Windows_Storage_Streams_IBuffer@UIBuffer@Streams@Storage@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Storage_Streams_IBuffer<winrt::Windows::Storage::Streams::IBuffer>::data(void)
0x1802e70ae  mov     qword ptr [rsp+68h+var_48], rdi
0x1802e70b3  mov     r9d, r12d
0x1802e70b6  mov     r8, rax
0x1802e70b9  mov     rdx, [rsi+20h]
0x1802e70bd  xor     ecx, ecx
0x1802e70bf  call    cs:__imp_imp_ApxStreamWriteData
0x1802e70c5  mov     rcx, [rsp+68h]; this
0x1802e70ca  lea     rdx, aApxstreamwrite; "ApxStreamWriteData failed"
0x1802e70d1  mov     qword ptr [rsp+68h+var_48], rdx; int
0x1802e70d6  mov     r9d, eax; char *
0x1802e70d9  lea     r8, aShellcommonUnd_89; "shellcommon\\undockeddevkit\\libs\\wind"...
0x1802e70e0  mov     edx, 120h; void *
0x1802e70e5  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1802e70ea  lea     rsi, [rbx-80h]
0x1802e70ee  mov     rcx, [rbx+40h]
0x1802e70f2  call    ?Size@?$consume_Windows_Foundation_Collections_IVector@U?$IVector@UCoreTextKeyFilter@Core@Text@Internal@UI@Windows@winrt@@@Collections@Foundation@Windows@winrt@@UCoreTextKeyFilter@Core@Text@Internal@UI@45@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::Windows::UI::Internal::Text::Core::CoreTextKeyFilter>,winrt::Windows::UI::Internal::Text::Core::CoreTextKeyFilter>::Size(void)
0x1802e70f7  lea     rdx, [rbx+1Ch]
0x1802e70fb  mov     [rdx], eax
0x1802e70fd  mov     rcx, rsi
0x1802e7100  call    ?return_value@promise_type@?$coroutine_traits@U?$IAsyncOperationWithProgress@II@Foundation@Windows@winrt@@PEAUVirtualAudioStreamOutputImpl@implementation@Devices@Media@WindowsUdk@4@AEBUIBuffer@Streams@Storage@34@@experimental@std@@QEAAX$$QEAI@Z; std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<uint,uint>,winrt::WindowsUdk::Media::Devices::implementation::VirtualAudioStreamOutputImpl *,winrt::Windows::Storage::Streams::IBuffer const &>::promise_type::return_value(uint &&)
0x1802e7105  nop
0x1802e7106  mov     rcx, r15; _Mtx_t
0x1802e7109  call    cs:__imp__Mtx_unlock
0x1802e710f  nop
0x1802e7110  jmp     short loc_1802E7141
0x1802e7112  lea     rsi, [rbx-80h]
0x1802e7116  lea     rdx, [rbx+18h]
0x1802e711a  mov     [rdx], edi
0x1802e711c  mov     rcx, rsi
0x1802e711f  call    ?return_value@promise_type@?$coroutine_traits@U?$IAsyncOperationWithProgress@II@Foundation@Windows@winrt@@PEAUVirtualAudioStreamOutputImpl@implementation@Devices@Media@WindowsUdk@4@AEBUIBuffer@Streams@Storage@34@@experimental@std@@QEAAX$$QEAI@Z; std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<uint,uint>,winrt::WindowsUdk::Media::Devices::implementation::VirtualAudioStreamOutputImpl *,winrt::Windows::Storage::Streams::IBuffer const &>::promise_type::return_value(uint &&)
0x1802e7124  nop
0x1802e7125  mov     rcx, r15; _Mtx_t
0x1802e7128  call    cs:__imp__Mtx_unlock
0x1802e712e  nop
0x1802e712f  jmp     short loc_1802E7141
0x1802e7131  mov     rbx, [rsp+68h+arg_0]
0x1802e7136  lea     rsi, [rbx-80h]
0x1802e713a  xor     edi, edi
0x1802e713c  mov     r14, [rsp+68h+arg_8]
0x1802e7141  lea     rcx, [rbx+20h]
0x1802e7145  mov     [rcx], rsi
0x1802e7148  xor     eax, eax
0x1802e714a  mov     [r14], ax
0x1802e714e  call    ?await_suspend@final_suspend_awaiter@?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@U?$IVectorView@UMenuItem@UI@WindowsUdk@winrt@@@Collections@Foundation@Windows@winrt@@@Foundation@Windows@winrt@@UIStorageItem@Storage@34@UUser@System@34@UMenuItemGetOptions@UI@WindowsUdk@4@@experimental@std@@U?$IAsyncOperation@U?$IVectorView@UMenuItem@UI@WindowsUdk@winrt@@@Collections@Foundation@Windows@winrt@@@Foundation@Windows@winrt@@X@impl@winrt@@QEBA_NU?$coroutine_handle@X@experimental@std@@@Z; winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Foundation::Collections::IVectorView<winrt::WindowsUdk::UI::MenuItem>>,winrt::Windows::Storage::IStorageItem,winrt::Windows::System::User,winrt::WindowsUdk::UI::MenuItemGetOptions>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Foundation::Collections::IVectorView<winrt::WindowsUdk::UI::MenuItem>>,void>::final_suspend_awaiter::await_suspend(std::experimental::coroutine_handle<void>)
0x1802e7153  test    al, al
0x1802e7155  jz      short loc_1802E715B
0x1802e7157  jmp     short loc_1802E717B
0x1802e7159  xor     edi, edi; jumptable 00000001802E704F cases -1,1
0x1802e715b  lea     rcx, [rbx-80h]
0x1802e715f  call    ??1promise_type@?$coroutine_traits@U?$IAsyncOperationWithProgress@II@Foundation@Windows@winrt@@PEAUVirtualAudioStreamOutputImpl@implementation@Devices@Media@WindowsUdk@4@AEBUIBuffer@Streams@Storage@34@@experimental@std@@UEAA@XZ; std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<uint,uint>,winrt::WindowsUdk::Media::Devices::implementation::VirtualAudioStreamOutputImpl *,winrt::Windows::Storage::Streams::IBuffer const &>::promise_type::~promise_type(void)
0x1802e7164  cmp     [rbx+0Ah], di
0x1802e7168  jz      short loc_1802E717B
0x1802e716a  mov     edx, 0D0h; struct std::nothrow_t *
0x1802e716f  lea     rcx, [rbx-80h]; void *
0x1802e7173  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1802e7178  jmp     short loc_1802E717B
0x1802e717a  int     3; Trap to Debugger
0x1802e717b  mov     rbx, [rsp+68h+arg_10]
0x1802e7183  add     rsp, 40h
0x1802e7187  pop     r15
0x1802e7189  pop     r14
0x1802e718b  pop     r12
0x1802e718d  pop     rdi
0x1802e718e  pop     rsi
0x1802e718f  retn
```
