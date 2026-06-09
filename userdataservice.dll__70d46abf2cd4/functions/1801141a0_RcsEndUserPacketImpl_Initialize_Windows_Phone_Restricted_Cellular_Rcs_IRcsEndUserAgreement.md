# RcsEndUserPacketImpl::_Initialize(Windows::Phone::Restricted::Cellular::Rcs::IRcsEndUserAgreement *)

- ea: `0x1801141a0`
- end: `0x18011441d`
- name: `?_Initialize@RcsEndUserPacketImpl@@AEAAJPEAUIRcsEndUserAgreement@Rcs@Cellular@Restricted@Phone@Windows@@@Z`
- size: `637`
- prototype: `__int64 __fastcall(RcsEndUserPacketImpl *__hidden this, struct Windows::Phone::Restricted::Cellular::Rcs::IRcsEndUserAgreement *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180111668`

## callees

- `0x180004658`
- `0x180035c40`
- `0x18008b320`
- `0x18008be00`
- `0x1801141a0`
- `0x18012e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801141d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18011420c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801143f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180114408`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801141d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18011420c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801143f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180114408`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18011437c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801143a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18011437c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801143a8`

## string_xrefs

- `0x18011423c`: `onecoreuap\base\appmodel\messagingom\utils\rcsserviceadapter\lib\rcsenduserpacketimpl.cpp`

## pseudocode

```c
__int64 __fastcall RcsEndUserPacketImpl::_Initialize(
        RcsEndUserPacketImpl *this,
        struct Windows::Phone::Restricted::Cellular::Rcs::IRcsEndUserAgreement *a2)
{
  __int64 v2; // rax
  __int64 (__fastcall *v5)(struct Windows::Phone::Restricted::Cellular::Rcs::IRcsEndUserAgreement *, HSTRING *); // rbx
  int TextForLabel; // eax
  unsigned int v7; // ebx
  __int64 (__fastcall *v8)(struct Windows::Phone::Restricted::Cellular::Rcs::IRcsEndUserAgreement *, HSTRING *); // rbx
  __int64 v9; // rdx
  __int64 v10; // rcx
  char *v11; // r8
  HSTRING v12; // rcx
  PCWSTR StringRawBuffer; // rax
  PCWSTR v14; // rax
  HSTRING v16; // [rsp+30h] [rbp-10h] BYREF
  __int64 v17; // [rsp+38h] [rbp-8h] BYREF
  char v18; // [rsp+68h] [rbp+28h] BYREF
  char v19; // [rsp+70h] [rbp+30h] BYREF
  HSTRING string; // [rsp+78h] [rbp+38h] BYREF

  v2 = *(_QWORD *)a2;
  v16 = 0;
  string = 0;
  v19 = 0;
  v5 = *(__int64 (__fastcall **)(struct Windows::Phone::Restricted::Cellular::Rcs::IRcsEndUserAgreement *, HSTRING *))(v2 + 64);
  v18 = 0;
  WindowsDeleteString(0);
  v16 = 0;
  TextForLabel = v5(a2, &v16);
  v7 = TextForLabel;
  if ( TextForLabel < 0 )
    goto LABEL_3;
  v8 = *(__int64 (__fastcall **)(struct Windows::Phone::Restricted::Cellular::Rcs::IRcsEndUserAgreement *, HSTRING *))(*(_QWORD *)a2 + 72LL);
  WindowsDeleteString(string);
  string = 0;
  TextForLabel = v8(a2, &string);
  v7 = TextForLabel;
  if ( TextForLabel < 0 )
    goto LABEL_3;
  TextForLabel = (*(__int64 (__fastcall **)(struct Windows::Phone::Restricted::Cellular::Rcs::IRcsEndUserAgreement *, char *))(*(_QWORD *)a2 + 48LL))(
                   a2,
                   &v19);
  v7 = TextForLabel;
  if ( TextForLabel < 0 )
    goto LABEL_3;
  TextForLabel = (*(__int64 (__fastcall **)(struct Windows::Phone::Restricted::Cellular::Rcs::IRcsEndUserAgreement *, char *))(*(_QWORD *)a2 + 56LL))(
                   a2,
                   &v18);
  v7 = TextForLabel;
  if ( TextForLabel < 0 )
    goto LABEL_3;
  if ( !v19 && !v18 )
  {
    v7 = -2147024809;
LABEL_10:
    v9 = 0;
    v10 = v7;
    goto LABEL_4;
  }
  v11 = (char *)this + 120;
  if ( !v18 )
  {
    TextForLabel = RcsEndUserPacketImpl::_GetTextForLabel(0, 17000, v11);
    v7 = TextForLabel;
    if ( TextForLabel >= 0 )
    {
      *((_DWORD *)this + 48) = 1;
      goto LABEL_20;
    }
    goto LABEL_3;
  }
  if ( !v19 )
  {
    TextForLabel = RcsEndUserPacketImpl::_GetTextForLabel(0, 17001, v11);
    v7 = TextForLabel;
    if ( TextForLabel >= 0 )
    {
      *((_DWORD *)this + 48) = 2;
      goto LABEL_20;
    }
LABEL_3:
    v9 = 1;
    v10 = (unsigned int)TextForLabel;
LABEL_4:
    Log_HREvent_38(
      v10,
      v9,
      "onecoreuap\\base\\appmodel\\messagingom\\utils\\rcsserviceadapter\\lib\\rcsenduserpacketimpl.cpp");
    goto LABEL_26;
  }
  TextForLabel = RcsEndUserPacketImpl::_GetTextForLabel(0, 17000, v11);
  v7 = TextForLabel;
  if ( TextForLabel < 0 )
    goto LABEL_3;
  *((_DWORD *)this + 48) = 1;
  TextForLabel = RcsEndUserPacketImpl::_GetTextForLabel(0, 17001, (char *)this + 152);
  v7 = TextForLabel;
  if ( TextForLabel < 0 )
    goto LABEL_3;
  *((_DWORD *)this + 49) = 2;
  *((_DWORD *)this + 46) = 1;
LABEL_20:
  v12 = v16;
  *((_DWORD *)this + 12) = 0;
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
    goto LABEL_10;
  }
  if ( *((struct Windows::Phone::Restricted::Cellular::Rcs::IRcsEndUserAgreement **)this + 3) != a2 )
  {
    (*(void (__fastcall **)(struct Windows::Phone::Restricted::Cellular::Rcs::IRcsEndUserAgreement *))(*(_QWORD *)a2 + 8LL))(a2);
    v17 = *((_QWORD *)this + 3);
    *((_QWORD *)this + 3) = a2;
    Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(&v17);
  }
  v7 = 0;
LABEL_26:
  WindowsDeleteString(string);
  string = 0;
  WindowsDeleteString(v16);
  return v7;
}

```

## disassembly

```asm
0x1801141a0  mov     [rsp-18h+arg_0], rbx
0x1801141a5  push    rbp
0x1801141a6  push    rsi
0x1801141a7  push    rdi
0x1801141a8  mov     rbp, rsp
0x1801141ab  sub     rsp, 40h
0x1801141af  mov     rax, [rdx]
0x1801141b2  mov     rdi, rcx
0x1801141b5  xor     ecx, ecx; string
0x1801141b7  mov     [rbp+var_10], 0
0x1801141bf  mov     rsi, rdx
0x1801141c2  mov     [rbp+string], 0
0x1801141ca  mov     [rbp+arg_10], 0
0x1801141ce  mov     rbx, [rax+40h]
0x1801141d2  mov     [rbp+arg_8], 0
0x1801141d6  call    cs:__imp_WindowsDeleteString
0x1801141dc  lea     rdx, [rbp+var_10]
0x1801141e0  mov     [rbp+var_10], 0
0x1801141e8  mov     rcx, rsi
0x1801141eb  mov     rax, rbx
0x1801141ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801141f3  mov     ebx, eax
0x1801141f5  test    eax, eax
0x1801141f7  jns     short loc_180114201
0x1801141f9  mov     r9d, 24h ; '$'
0x1801141ff  jmp     short loc_180114235
0x180114201  mov     rax, [rsi]
0x180114204  mov     rcx, [rbp+string]; string
0x180114208  mov     rbx, [rax+48h]
0x18011420c  call    cs:__imp_WindowsDeleteString
0x180114212  lea     rdx, [rbp+string]
0x180114216  mov     [rbp+string], 0
0x18011421e  mov     rcx, rsi
0x180114221  mov     rax, rbx
0x180114224  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180114229  mov     ebx, eax
0x18011422b  test    eax, eax
0x18011422d  jns     short loc_18011424D
0x18011422f  mov     r9d, 25h ; '%'
0x180114235  mov     edx, 1
0x18011423a  mov     ecx, eax
0x18011423c  lea     r8, aOnecoreuapBase_85; "onecoreuap\\base\\appmodel\\messagingom"...
0x180114243  call    Log_HREvent_38
0x180114248  jmp     loc_1801143F2
0x18011424d  mov     rax, [rsi]
0x180114250  lea     rdx, [rbp+arg_10]
0x180114254  mov     rcx, rsi
0x180114257  mov     rax, [rax+30h]
0x18011425b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180114260  mov     ebx, eax
0x180114262  test    eax, eax
0x180114264  jns     short loc_18011426E
0x180114266  mov     r9d, 26h ; '&'
0x18011426c  jmp     short loc_180114235
0x18011426e  mov     rax, [rsi]
0x180114271  lea     rdx, [rbp+arg_8]
0x180114275  mov     rcx, rsi
0x180114278  mov     rax, [rax+38h]
0x18011427c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180114281  mov     ebx, eax
0x180114283  test    eax, eax
0x180114285  jns     short loc_18011428F
0x180114287  mov     r9d, 27h ; '''
0x18011428d  jmp     short loc_180114235
0x18011428f  mov     cl, [rbp+arg_10]
0x180114292  mov     al, [rbp+arg_8]
0x180114295  test    cl, cl
0x180114297  jnz     short loc_1801142AE
0x180114299  test    al, al
0x18011429b  jnz     short loc_1801142AE
0x18011429d  mov     r9d, 2Ah ; '*'
0x1801142a3  mov     ebx, 80070057h
0x1801142a8  xor     edx, edx
0x1801142aa  mov     ecx, ebx
0x1801142ac  jmp     short loc_18011423C
0x1801142ae  lea     r8, [rdi+78h]
0x1801142b2  test    al, al
0x1801142b4  jz      loc_180114348
0x1801142ba  test    cl, cl
0x1801142bc  jz      short loc_18011431F
0x1801142be  mov     edx, 4268h
0x1801142c3  xor     ecx, ecx
0x1801142c5  call    ?_GetTextForLabel@RcsEndUserPacketImpl@@CAJPEAVHString@Wrappers@WRL@Microsoft@@IPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; RcsEndUserPacketImpl::_GetTextForLabel(Microsoft::WRL::Wrappers::HString *,uint,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)
0x1801142ca  mov     ebx, eax
0x1801142cc  test    eax, eax
0x1801142ce  jns     short loc_1801142DB
0x1801142d0  mov     r9d, 30h ; '0'
0x1801142d6  jmp     loc_180114235
0x1801142db  lea     r8, [rdi+98h]
0x1801142e2  mov     dword ptr [rdi+0C0h], 1
0x1801142ec  mov     edx, 4269h
0x1801142f1  xor     ecx, ecx
0x1801142f3  call    ?_GetTextForLabel@RcsEndUserPacketImpl@@CAJPEAVHString@Wrappers@WRL@Microsoft@@IPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; RcsEndUserPacketImpl::_GetTextForLabel(Microsoft::WRL::Wrappers::HString *,uint,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)
0x1801142f8  mov     ebx, eax
0x1801142fa  test    eax, eax
0x1801142fc  jns     short loc_180114309
0x1801142fe  mov     r9d, 33h ; '3'
0x180114304  jmp     loc_180114235
0x180114309  mov     dword ptr [rdi+0C4h], 2
0x180114313  mov     dword ptr [rdi+0B8h], 1
0x18011431d  jmp     short loc_18011436F
0x18011431f  mov     edx, 4269h
0x180114324  xor     ecx, ecx
0x180114326  call    ?_GetTextForLabel@RcsEndUserPacketImpl@@CAJPEAVHString@Wrappers@WRL@Microsoft@@IPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; RcsEndUserPacketImpl::_GetTextForLabel(Microsoft::WRL::Wrappers::HString *,uint,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)
0x18011432b  mov     ebx, eax
0x18011432d  test    eax, eax
0x18011432f  jns     short loc_18011433C
0x180114331  mov     r9d, 39h ; '9'
0x180114337  jmp     loc_180114235
0x18011433c  mov     dword ptr [rdi+0C0h], 2
0x180114346  jmp     short loc_18011436F
0x180114348  mov     edx, 4268h
0x18011434d  xor     ecx, ecx
0x18011434f  call    ?_GetTextForLabel@RcsEndUserPacketImpl@@CAJPEAVHString@Wrappers@WRL@Microsoft@@IPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; RcsEndUserPacketImpl::_GetTextForLabel(Microsoft::WRL::Wrappers::HString *,uint,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)
0x180114354  mov     ebx, eax
0x180114356  test    eax, eax
0x180114358  jns     short loc_180114365
0x18011435a  mov     r9d, 40h ; '@'
0x180114360  jmp     loc_180114235
0x180114365  mov     dword ptr [rdi+0C0h], 1
0x18011436f  mov     rcx, [rbp+var_10]; string
0x180114373  xor     edx, edx; length
0x180114375  mov     dword ptr [rdi+30h], 0
0x18011437c  call    cs:__imp_WindowsGetStringRawBuffer
0x180114382  mov     rdx, rax
0x180114385  lea     rcx, [rdi+38h]
0x180114389  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x18011438e  test    al, al
0x180114390  jnz     short loc_1801143A2
0x180114392  mov     r9d, 46h ; 'F'
0x180114398  mov     ebx, 8007000Eh
0x18011439d  jmp     loc_1801142A8
0x1801143a2  mov     rcx, [rbp+string]; string
0x1801143a6  xor     edx, edx; length
0x1801143a8  call    cs:__imp_WindowsGetStringRawBuffer
0x1801143ae  mov     rdx, rax
0x1801143b1  lea     rcx, [rdi+58h]
0x1801143b5  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x1801143ba  test    al, al
0x1801143bc  jnz     short loc_1801143C6
0x1801143be  mov     r9d, 47h ; 'G'
0x1801143c4  jmp     short loc_180114398
0x1801143c6  cmp     [rdi+18h], rsi
0x1801143ca  jz      short loc_1801143F0
0x1801143cc  mov     rax, [rsi]
0x1801143cf  mov     rcx, rsi
0x1801143d2  mov     rax, [rax+8]
0x1801143d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801143db  mov     rax, [rdi+18h]
0x1801143df  lea     rcx, [rbp+var_8]
0x1801143e3  mov     [rbp+var_8], rax
0x1801143e7  mov     [rdi+18h], rsi
0x1801143eb  call    ?InternalRelease@?$ComPtr@U?$OperationCallback@PEAVAccount@Sync@Experiences@PhoneInternal@@@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(void)
0x1801143f0  xor     ebx, ebx
0x1801143f2  mov     rcx, [rbp+string]; string
0x1801143f6  call    cs:__imp_WindowsDeleteString
0x1801143fc  mov     rcx, [rbp+var_10]; string
0x180114400  mov     [rbp+string], 0
0x180114408  call    cs:__imp_WindowsDeleteString
0x18011440e  mov     eax, ebx
0x180114410  mov     rbx, [rsp+40h+arg_0]
0x180114415  add     rsp, 40h
0x180114419  pop     rdi
0x18011441a  pop     rsi
0x18011441b  pop     rbp
0x18011441c  retn
```
