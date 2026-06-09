# RcsEndUserPacketImpl::_Initialize(Windows::Phone::Restricted::Cellular::Rcs::IRcsEndUserConfirmationRequest *)

- ea: `0x180114424`
- end: `0x1801146af`
- name: `?_Initialize@RcsEndUserPacketImpl@@AEAAJPEAUIRcsEndUserConfirmationRequest@Rcs@Cellular@Restricted@Phone@Windows@@@Z`
- size: `651`
- prototype: `__int64 __fastcall(RcsEndUserPacketImpl *__hidden this, struct Windows::Phone::Restricted::Cellular::Rcs::IRcsEndUserConfirmationRequest *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18011172c`

## callees

- `0x180004658`
- `0x180035c40`
- `0x18008b320`
- `0x18008be00`
- `0x180114424`
- `0x18012e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18011445c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18011448c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801144d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180114506`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180114672`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180114680`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18011468e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18011469c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18011445c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18011448c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801144d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180114506`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180114672`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180114680`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18011468e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18011469c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180114582`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801145b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180114582`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801145b2`

## string_xrefs

- `0x1801144b8`: `onecoreuap\base\appmodel\messagingom\utils\rcsserviceadapter\lib\rcsenduserpacketimpl.cpp`

## pseudocode

```c
__int64 __fastcall RcsEndUserPacketImpl::_Initialize(
        RcsEndUserPacketImpl *this,
        struct Windows::Phone::Restricted::Cellular::Rcs::IRcsEndUserConfirmationRequest *a2)
{
  __int64 v2; // rax
  __int64 (__fastcall *v5)(struct Windows::Phone::Restricted::Cellular::Rcs::IRcsEndUserConfirmationRequest *, HSTRING *); // rbx
  int TextForLabel; // eax
  unsigned int v7; // ebx
  __int64 (__fastcall *v8)(struct Windows::Phone::Restricted::Cellular::Rcs::IRcsEndUserConfirmationRequest *, HSTRING *); // rbx
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 (__fastcall *v11)(struct Windows::Phone::Restricted::Cellular::Rcs::IRcsEndUserConfirmationRequest *, HSTRING *); // rbx
  __int64 (__fastcall *v12)(struct Windows::Phone::Restricted::Cellular::Rcs::IRcsEndUserConfirmationRequest *, HSTRING *); // rbx
  HSTRING v13; // rcx
  PCWSTR StringRawBuffer; // rax
  PCWSTR v15; // rax
  HSTRING v17; // [rsp+30h] [rbp-20h] BYREF
  HSTRING string; // [rsp+38h] [rbp-18h] BYREF
  HSTRING v19; // [rsp+40h] [rbp-10h] BYREF
  __int64 v20; // [rsp+48h] [rbp-8h] BYREF
  unsigned __int8 v21; // [rsp+88h] [rbp+38h] BYREF
  int v22; // [rsp+90h] [rbp+40h] BYREF
  HSTRING v23; // [rsp+98h] [rbp+48h] BYREF

  v2 = *(_QWORD *)a2;
  v19 = 0;
  string = 0;
  v17 = 0;
  v5 = *(__int64 (__fastcall **)(struct Windows::Phone::Restricted::Cellular::Rcs::IRcsEndUserConfirmationRequest *, HSTRING *))(v2 + 64);
  v23 = 0;
  v21 = 0;
  v22 = 0;
  WindowsDeleteString(0);
  v19 = 0;
  TextForLabel = v5(a2, &v19);
  v7 = TextForLabel;
  if ( TextForLabel < 0 )
    goto LABEL_3;
  v8 = *(__int64 (__fastcall **)(struct Windows::Phone::Restricted::Cellular::Rcs::IRcsEndUserConfirmationRequest *, HSTRING *))(*(_QWORD *)a2 + 72LL);
  WindowsDeleteString(string);
  string = 0;
  TextForLabel = v8(a2, &string);
  v7 = TextForLabel;
  if ( TextForLabel < 0 )
    goto LABEL_3;
  v11 = *(__int64 (__fastcall **)(struct Windows::Phone::Restricted::Cellular::Rcs::IRcsEndUserConfirmationRequest *, HSTRING *))(*(_QWORD *)a2 + 48LL);
  WindowsDeleteString(v17);
  v17 = 0;
  TextForLabel = v11(a2, &v17);
  v7 = TextForLabel;
  if ( TextForLabel < 0 )
    goto LABEL_3;
  v12 = *(__int64 (__fastcall **)(struct Windows::Phone::Restricted::Cellular::Rcs::IRcsEndUserConfirmationRequest *, HSTRING *))(*(_QWORD *)a2 + 56LL);
  WindowsDeleteString(v23);
  v23 = 0;
  TextForLabel = v12(a2, &v23);
  v7 = TextForLabel;
  if ( TextForLabel < 0 )
    goto LABEL_3;
  TextForLabel = (*(__int64 (__fastcall **)(struct Windows::Phone::Restricted::Cellular::Rcs::IRcsEndUserConfirmationRequest *, unsigned __int8 *))(*(_QWORD *)a2 + 88LL))(
                   a2,
                   &v21);
  v7 = TextForLabel;
  if ( TextForLabel < 0 )
    goto LABEL_3;
  TextForLabel = (*(__int64 (__fastcall **)(struct Windows::Phone::Restricted::Cellular::Rcs::IRcsEndUserConfirmationRequest *, int *))(*(_QWORD *)a2 + 80LL))(
                   a2,
                   &v22);
  v7 = TextForLabel;
  if ( TextForLabel < 0 )
    goto LABEL_3;
  v13 = v19;
  *((_DWORD *)this + 12) = 1;
  StringRawBuffer = WindowsGetStringRawBuffer(v13, 0);
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           (char *)this + 56,
                           StringRawBuffer)
    || (v15 = WindowsGetStringRawBuffer(string, 0),
        !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                            (char *)this + 88,
                            v15)) )
  {
    v7 = -2147024882;
    v9 = 0;
    v10 = 2147942414LL;
    goto LABEL_4;
  }
  TextForLabel = RcsEndUserPacketImpl::_GetTextForLabel(&v17, 17000, (char *)this + 120);
  v7 = TextForLabel;
  if ( TextForLabel < 0
    || (*((_DWORD *)this + 48) = 1,
        TextForLabel = RcsEndUserPacketImpl::_GetTextForLabel(&v23, 17001, (char *)this + 152),
        v7 = TextForLabel,
        TextForLabel < 0) )
  {
LABEL_3:
    v9 = 1;
    v10 = (unsigned int)TextForLabel;
LABEL_4:
    Log_HREvent_38(
      v10,
      v9,
      "onecoreuap\\base\\appmodel\\messagingom\\utils\\rcsserviceadapter\\lib\\rcsenduserpacketimpl.cpp");
    goto LABEL_17;
  }
  *((_DWORD *)this + 47) = v21;
  *((_DWORD *)this + 49) = 2;
  *((_DWORD *)this + 46) = 1;
  if ( *((struct Windows::Phone::Restricted::Cellular::Rcs::IRcsEndUserConfirmationRequest **)this + 4) != a2 )
  {
    (*(void (__fastcall **)(struct Windows::Phone::Restricted::Cellular::Rcs::IRcsEndUserConfirmationRequest *))(*(_QWORD *)a2 + 8LL))(a2);
    v20 = *((_QWORD *)this + 4);
    *((_QWORD *)this + 4) = a2;
    Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(&v20);
  }
  v7 = 0;
LABEL_17:
  WindowsDeleteString(v23);
  v23 = 0;
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
0x180114424  push    rbp
0x180114426  push    rbx
0x180114427  push    rsi
0x180114428  push    rdi
0x180114429  push    r14
0x18011442b  mov     rbp, rsp
0x18011442e  sub     rsp, 50h
0x180114432  mov     rax, [rdx]
0x180114435  xor     r14d, r14d
0x180114438  mov     rdi, rcx
0x18011443b  mov     [rbp+var_10], r14
0x18011443f  xor     ecx, ecx; string
0x180114441  mov     [rbp+string], r14
0x180114445  mov     rsi, rdx
0x180114448  mov     [rbp+var_20], r14
0x18011444c  mov     rbx, [rax+40h]
0x180114450  mov     [rbp+arg_18], r14
0x180114454  mov     [rbp+arg_8], r14b
0x180114458  mov     [rbp+arg_10], r14d
0x18011445c  call    cs:__imp_WindowsDeleteString
0x180114462  lea     rdx, [rbp+var_10]
0x180114466  mov     [rbp+var_10], r14
0x18011446a  mov     rcx, rsi
0x18011446d  mov     rax, rbx
0x180114470  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180114475  mov     ebx, eax
0x180114477  test    eax, eax
0x180114479  jns     short loc_180114481
0x18011447b  lea     r9d, [r14+56h]
0x18011447f  jmp     short loc_1801144B1
0x180114481  mov     rax, [rsi]
0x180114484  mov     rcx, [rbp+string]; string
0x180114488  mov     rbx, [rax+48h]
0x18011448c  call    cs:__imp_WindowsDeleteString
0x180114492  lea     rdx, [rbp+string]
0x180114496  mov     [rbp+string], r14
0x18011449a  mov     rcx, rsi
0x18011449d  mov     rax, rbx
0x1801144a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801144a5  mov     ebx, eax
0x1801144a7  test    eax, eax
0x1801144a9  jns     short loc_1801144C9
0x1801144ab  mov     r9d, 57h ; 'W'
0x1801144b1  mov     edx, 1
0x1801144b6  mov     ecx, eax
0x1801144b8  lea     r8, aOnecoreuapBase_85; "onecoreuap\\base\\appmodel\\messagingom"...
0x1801144bf  call    Log_HREvent_38
0x1801144c4  jmp     loc_18011466E
0x1801144c9  mov     rax, [rsi]
0x1801144cc  mov     rcx, [rbp+var_20]; string
0x1801144d0  mov     rbx, [rax+30h]
0x1801144d4  call    cs:__imp_WindowsDeleteString
0x1801144da  lea     rdx, [rbp+var_20]
0x1801144de  mov     [rbp+var_20], r14
0x1801144e2  mov     rcx, rsi
0x1801144e5  mov     rax, rbx
0x1801144e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801144ed  mov     ebx, eax
0x1801144ef  test    eax, eax
0x1801144f1  jns     short loc_1801144FB
0x1801144f3  mov     r9d, 58h ; 'X'
0x1801144f9  jmp     short loc_1801144B1
0x1801144fb  mov     rax, [rsi]
0x1801144fe  mov     rcx, [rbp+arg_18]; string
0x180114502  mov     rbx, [rax+38h]
0x180114506  call    cs:__imp_WindowsDeleteString
0x18011450c  lea     rdx, [rbp+arg_18]
0x180114510  mov     [rbp+arg_18], r14
0x180114514  mov     rcx, rsi
0x180114517  mov     rax, rbx
0x18011451a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011451f  mov     ebx, eax
0x180114521  test    eax, eax
0x180114523  jns     short loc_18011452D
0x180114525  mov     r9d, 59h ; 'Y'
0x18011452b  jmp     short loc_1801144B1
0x18011452d  mov     rax, [rsi]
0x180114530  lea     rdx, [rbp+arg_8]
0x180114534  mov     rcx, rsi
0x180114537  mov     rax, [rax+58h]
0x18011453b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180114540  mov     ebx, eax
0x180114542  test    eax, eax
0x180114544  jns     short loc_180114551
0x180114546  mov     r9d, 5Ah ; 'Z'
0x18011454c  jmp     loc_1801144B1
0x180114551  mov     rax, [rsi]
0x180114554  lea     rdx, [rbp+arg_10]
0x180114558  mov     rcx, rsi
0x18011455b  mov     rax, [rax+50h]
0x18011455f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180114564  mov     ebx, eax
0x180114566  test    eax, eax
0x180114568  jns     short loc_180114575
0x18011456a  mov     r9d, 5Bh ; '['
0x180114570  jmp     loc_1801144B1
0x180114575  mov     rcx, [rbp+var_10]; string
0x180114579  xor     edx, edx; length
0x18011457b  mov     dword ptr [rdi+30h], 1
0x180114582  call    cs:__imp_WindowsGetStringRawBuffer
0x180114588  mov     rdx, rax
0x18011458b  lea     rcx, [rdi+38h]
0x18011458f  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x180114594  test    al, al
0x180114596  jnz     short loc_1801145AC
0x180114598  mov     r9d, 5Fh ; '_'
0x18011459e  mov     ebx, 8007000Eh
0x1801145a3  xor     edx, edx
0x1801145a5  mov     ecx, ebx
0x1801145a7  jmp     loc_1801144B8
0x1801145ac  mov     rcx, [rbp+string]; string
0x1801145b0  xor     edx, edx; length
0x1801145b2  call    cs:__imp_WindowsGetStringRawBuffer
0x1801145b8  mov     rdx, rax
0x1801145bb  lea     rcx, [rdi+58h]
0x1801145bf  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x1801145c4  test    al, al
0x1801145c6  jnz     short loc_1801145D0
0x1801145c8  mov     r9d, 60h ; '`'
0x1801145ce  jmp     short loc_18011459E
0x1801145d0  lea     r8, [rdi+78h]
0x1801145d4  mov     edx, 4268h
0x1801145d9  lea     rcx, [rbp+var_20]
0x1801145dd  call    ?_GetTextForLabel@RcsEndUserPacketImpl@@CAJPEAVHString@Wrappers@WRL@Microsoft@@IPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; RcsEndUserPacketImpl::_GetTextForLabel(Microsoft::WRL::Wrappers::HString *,uint,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)
0x1801145e2  mov     ebx, eax
0x1801145e4  test    eax, eax
0x1801145e6  jns     short loc_1801145F3
0x1801145e8  mov     r9d, 62h ; 'b'
0x1801145ee  jmp     loc_1801144B1
0x1801145f3  lea     r8, [rdi+98h]
0x1801145fa  mov     dword ptr [rdi+0C0h], 1
0x180114604  mov     edx, 4269h
0x180114609  lea     rcx, [rbp+arg_18]
0x18011460d  call    ?_GetTextForLabel@RcsEndUserPacketImpl@@CAJPEAVHString@Wrappers@WRL@Microsoft@@IPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; RcsEndUserPacketImpl::_GetTextForLabel(Microsoft::WRL::Wrappers::HString *,uint,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)
0x180114612  mov     ebx, eax
0x180114614  test    eax, eax
0x180114616  jns     short loc_180114623
0x180114618  mov     r9d, 65h ; 'e'
0x18011461e  jmp     loc_1801144B1
0x180114623  movzx   eax, [rbp+arg_8]
0x180114627  mov     [rdi+0BCh], eax
0x18011462d  mov     dword ptr [rdi+0C4h], 2
0x180114637  mov     dword ptr [rdi+0B8h], 1
0x180114641  cmp     [rdi+20h], rsi
0x180114645  jz      short loc_18011466B
0x180114647  mov     rax, [rsi]
0x18011464a  mov     rcx, rsi
0x18011464d  mov     rax, [rax+8]
0x180114651  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180114656  mov     rax, [rdi+20h]
0x18011465a  lea     rcx, [rbp+var_8]
0x18011465e  mov     [rbp+var_8], rax
0x180114662  mov     [rdi+20h], rsi
0x180114666  call    ?InternalRelease@?$ComPtr@U?$OperationCallback@PEAVAccount@Sync@Experiences@PhoneInternal@@@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(void)
0x18011466b  mov     ebx, r14d
0x18011466e  mov     rcx, [rbp+arg_18]; string
0x180114672  call    cs:__imp_WindowsDeleteString
0x180114678  mov     rcx, [rbp+var_20]; string
0x18011467c  mov     [rbp+arg_18], r14
0x180114680  call    cs:__imp_WindowsDeleteString
0x180114686  mov     rcx, [rbp+string]; string
0x18011468a  mov     [rbp+var_20], r14
0x18011468e  call    cs:__imp_WindowsDeleteString
0x180114694  mov     rcx, [rbp+var_10]; string
0x180114698  mov     [rbp+string], r14
0x18011469c  call    cs:__imp_WindowsDeleteString
0x1801146a2  mov     eax, ebx
0x1801146a4  add     rsp, 50h
0x1801146a8  pop     r14
0x1801146aa  pop     rdi
0x1801146ab  pop     rsi
0x1801146ac  pop     rbx
0x1801146ad  pop     rbp
0x1801146ae  retn
```
