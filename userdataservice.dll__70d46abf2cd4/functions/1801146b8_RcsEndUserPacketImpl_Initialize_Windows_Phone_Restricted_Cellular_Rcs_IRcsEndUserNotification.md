# RcsEndUserPacketImpl::_Initialize(Windows::Phone::Restricted::Cellular::Rcs::IRcsEndUserNotification *)

- ea: `0x1801146b8`
- end: `0x180114889`
- name: `?_Initialize@RcsEndUserPacketImpl@@AEAAJPEAUIRcsEndUserNotification@Rcs@Cellular@Restricted@Phone@Windows@@@Z`
- size: `465`
- prototype: `__int64 __fastcall(RcsEndUserPacketImpl *__hidden this, struct Windows::Phone::Restricted::Cellular::Rcs::IRcsEndUserNotification *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x1801117f0`

## callees

- `0x180004658`
- `0x180035c40`
- `0x18008b320`
- `0x18008be00`
- `0x1801146b8`
- `0x18012e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801146ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180114724`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180114770`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180114850`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180114862`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180114874`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801146ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180114724`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180114770`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180114850`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180114862`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180114874`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801147a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801147d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801147a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801147d5`

## string_xrefs

- `0x180114754`: `onecoreuap\base\appmodel\messagingom\utils\rcsserviceadapter\lib\rcsenduserpacketimpl.cpp`

## pseudocode

```c
__int64 __fastcall RcsEndUserPacketImpl::_Initialize(
        RcsEndUserPacketImpl *this,
        struct Windows::Phone::Restricted::Cellular::Rcs::IRcsEndUserNotification *a2)
{
  __int64 v2; // rax
  __int64 (__fastcall *v5)(struct Windows::Phone::Restricted::Cellular::Rcs::IRcsEndUserNotification *, HSTRING *); // rbx
  int TextForLabel; // eax
  unsigned int v7; // ebx
  __int64 (__fastcall *v8)(struct Windows::Phone::Restricted::Cellular::Rcs::IRcsEndUserNotification *, HSTRING *); // rbx
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 (__fastcall *v11)(struct Windows::Phone::Restricted::Cellular::Rcs::IRcsEndUserNotification *, HSTRING *); // rbx
  HSTRING v12; // rcx
  PCWSTR StringRawBuffer; // rax
  PCWSTR v14; // rax
  __int64 v16; // [rsp+30h] [rbp-10h] BYREF
  HSTRING v17; // [rsp+68h] [rbp+28h] BYREF
  HSTRING string; // [rsp+70h] [rbp+30h] BYREF
  HSTRING v19; // [rsp+78h] [rbp+38h] BYREF

  v2 = *(_QWORD *)a2;
  v19 = 0;
  string = 0;
  v17 = 0;
  v5 = *(__int64 (__fastcall **)(struct Windows::Phone::Restricted::Cellular::Rcs::IRcsEndUserNotification *, HSTRING *))(v2 + 56);
  WindowsDeleteString(0);
  v19 = 0;
  TextForLabel = v5(a2, &v19);
  v7 = TextForLabel;
  if ( TextForLabel < 0 )
    goto LABEL_3;
  v8 = *(__int64 (__fastcall **)(struct Windows::Phone::Restricted::Cellular::Rcs::IRcsEndUserNotification *, HSTRING *))(*(_QWORD *)a2 + 64LL);
  WindowsDeleteString(string);
  string = 0;
  TextForLabel = v8(a2, &string);
  v7 = TextForLabel;
  if ( TextForLabel < 0 )
    goto LABEL_3;
  v11 = *(__int64 (__fastcall **)(struct Windows::Phone::Restricted::Cellular::Rcs::IRcsEndUserNotification *, HSTRING *))(*(_QWORD *)a2 + 48LL);
  WindowsDeleteString(v17);
  v17 = 0;
  TextForLabel = v11(a2, &v17);
  v7 = TextForLabel;
  if ( TextForLabel < 0 )
    goto LABEL_3;
  v12 = v19;
  *((_DWORD *)this + 12) = 2;
  StringRawBuffer = WindowsGetStringRawBuffer(v12, 0);
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           (char *)this + 56,
                           StringRawBuffer)
    || (v14 = WindowsGetStringRawBuffer(string, 0),
        !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                            (char *)this + 88,
                            v14)) )
  {
    v7 = -2147024882;
    v9 = 0;
    v10 = 2147942414LL;
    goto LABEL_4;
  }
  TextForLabel = RcsEndUserPacketImpl::_GetTextForLabel(&v17, 17002, (char *)this + 120);
  v7 = TextForLabel;
  if ( TextForLabel < 0 )
  {
LABEL_3:
    v9 = 1;
    v10 = (unsigned int)TextForLabel;
LABEL_4:
    Log_HREvent_38(
      v10,
      v9,
      "onecoreuap\\base\\appmodel\\messagingom\\utils\\rcsserviceadapter\\lib\\rcsenduserpacketimpl.cpp");
    goto LABEL_13;
  }
  *((_DWORD *)this + 48) = 3;
  if ( *((struct Windows::Phone::Restricted::Cellular::Rcs::IRcsEndUserNotification **)this + 5) != a2 )
  {
    (*(void (__fastcall **)(struct Windows::Phone::Restricted::Cellular::Rcs::IRcsEndUserNotification *))(*(_QWORD *)a2 + 8LL))(a2);
    v16 = *((_QWORD *)this + 5);
    *((_QWORD *)this + 5) = a2;
    Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(&v16);
  }
  v7 = 0;
LABEL_13:
  WindowsDeleteString(v17);
  v17 = 0;
  WindowsDeleteString(string);
  string = 0;
  WindowsDeleteString(v19);
  return v7;
}

```

## disassembly

```asm
0x1801146b8  mov     [rsp-18h+arg_0], rbx
0x1801146bd  push    rbp
0x1801146be  push    rsi
0x1801146bf  push    rdi
0x1801146c0  mov     rbp, rsp
0x1801146c3  sub     rsp, 40h
0x1801146c7  mov     rax, [rdx]
0x1801146ca  mov     rdi, rcx
0x1801146cd  xor     ecx, ecx; string
0x1801146cf  mov     [rbp+arg_18], 0
0x1801146d7  mov     rsi, rdx
0x1801146da  mov     [rbp+string], 0
0x1801146e2  mov     [rbp+arg_8], 0
0x1801146ea  mov     rbx, [rax+38h]
0x1801146ee  call    cs:__imp_WindowsDeleteString
0x1801146f4  lea     rdx, [rbp+arg_18]
0x1801146f8  mov     [rbp+arg_18], 0
0x180114700  mov     rcx, rsi
0x180114703  mov     rax, rbx
0x180114706  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011470b  mov     ebx, eax
0x18011470d  test    eax, eax
0x18011470f  jns     short loc_180114719
0x180114711  mov     r9d, 75h ; 'u'
0x180114717  jmp     short loc_18011474D
0x180114719  mov     rax, [rsi]
0x18011471c  mov     rcx, [rbp+string]; string
0x180114720  mov     rbx, [rax+40h]
0x180114724  call    cs:__imp_WindowsDeleteString
0x18011472a  lea     rdx, [rbp+string]
0x18011472e  mov     [rbp+string], 0
0x180114736  mov     rcx, rsi
0x180114739  mov     rax, rbx
0x18011473c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180114741  mov     ebx, eax
0x180114743  test    eax, eax
0x180114745  jns     short loc_180114765
0x180114747  mov     r9d, 76h ; 'v'
0x18011474d  mov     edx, 1
0x180114752  mov     ecx, eax
0x180114754  lea     r8, aOnecoreuapBase_85; "onecoreuap\\base\\appmodel\\messagingom"...
0x18011475b  call    Log_HREvent_38
0x180114760  jmp     loc_18011484C
0x180114765  mov     rax, [rsi]
0x180114768  mov     rcx, [rbp+arg_8]; string
0x18011476c  mov     rbx, [rax+30h]
0x180114770  call    cs:__imp_WindowsDeleteString
0x180114776  lea     rdx, [rbp+arg_8]
0x18011477a  mov     [rbp+arg_8], 0
0x180114782  mov     rcx, rsi
0x180114785  mov     rax, rbx
0x180114788  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011478d  mov     ebx, eax
0x18011478f  test    eax, eax
0x180114791  jns     short loc_18011479B
0x180114793  mov     r9d, 77h ; 'w'
0x180114799  jmp     short loc_18011474D
0x18011479b  mov     rcx, [rbp+arg_18]; string
0x18011479f  xor     edx, edx; length
0x1801147a1  mov     dword ptr [rdi+30h], 2
0x1801147a8  call    cs:__imp_WindowsGetStringRawBuffer
0x1801147ae  mov     rdx, rax
0x1801147b1  lea     rcx, [rdi+38h]
0x1801147b5  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x1801147ba  test    al, al
0x1801147bc  jnz     short loc_1801147CF
0x1801147be  mov     r9d, 7Bh ; '{'
0x1801147c4  mov     ebx, 8007000Eh
0x1801147c9  xor     edx, edx
0x1801147cb  mov     ecx, ebx
0x1801147cd  jmp     short loc_180114754
0x1801147cf  mov     rcx, [rbp+string]; string
0x1801147d3  xor     edx, edx; length
0x1801147d5  call    cs:__imp_WindowsGetStringRawBuffer
0x1801147db  mov     rdx, rax
0x1801147de  lea     rcx, [rdi+58h]
0x1801147e2  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x1801147e7  test    al, al
0x1801147e9  jnz     short loc_1801147F3
0x1801147eb  mov     r9d, 7Ch ; '|'
0x1801147f1  jmp     short loc_1801147C4
0x1801147f3  lea     r8, [rdi+78h]
0x1801147f7  mov     edx, 426Ah
0x1801147fc  lea     rcx, [rbp+arg_8]
0x180114800  call    ?_GetTextForLabel@RcsEndUserPacketImpl@@CAJPEAVHString@Wrappers@WRL@Microsoft@@IPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; RcsEndUserPacketImpl::_GetTextForLabel(Microsoft::WRL::Wrappers::HString *,uint,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)
0x180114805  mov     ebx, eax
0x180114807  test    eax, eax
0x180114809  jns     short loc_180114816
0x18011480b  mov     r9d, 7Eh ; '~'
0x180114811  jmp     loc_18011474D
0x180114816  mov     dword ptr [rdi+0C0h], 3
0x180114820  cmp     [rdi+28h], rsi
0x180114824  jz      short loc_18011484A
0x180114826  mov     rax, [rsi]
0x180114829  mov     rcx, rsi
0x18011482c  mov     rax, [rax+8]
0x180114830  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180114835  mov     rax, [rdi+28h]
0x180114839  lea     rcx, [rbp+var_10]
0x18011483d  mov     [rbp+var_10], rax
0x180114841  mov     [rdi+28h], rsi
0x180114845  call    ?InternalRelease@?$ComPtr@U?$OperationCallback@PEAVAccount@Sync@Experiences@PhoneInternal@@@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(void)
0x18011484a  xor     ebx, ebx
0x18011484c  mov     rcx, [rbp+arg_8]; string
0x180114850  call    cs:__imp_WindowsDeleteString
0x180114856  mov     rcx, [rbp+string]; string
0x18011485a  mov     [rbp+arg_8], 0
0x180114862  call    cs:__imp_WindowsDeleteString
0x180114868  mov     rcx, [rbp+arg_18]; string
0x18011486c  mov     [rbp+string], 0
0x180114874  call    cs:__imp_WindowsDeleteString
0x18011487a  mov     eax, ebx
0x18011487c  mov     rbx, [rsp+40h+arg_0]
0x180114881  add     rsp, 40h
0x180114885  pop     rdi
0x180114886  pop     rsi
0x180114887  pop     rbp
0x180114888  retn
```
