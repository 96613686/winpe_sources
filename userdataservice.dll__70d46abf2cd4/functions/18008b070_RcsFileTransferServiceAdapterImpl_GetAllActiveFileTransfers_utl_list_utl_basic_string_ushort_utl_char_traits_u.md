# RcsFileTransferServiceAdapterImpl::GetAllActiveFileTransfers(utl::list<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>> *)

- ea: `0x18008b070`
- end: `0x18008b317`
- name: `?GetAllActiveFileTransfers@RcsFileTransferServiceAdapterImpl@@UEAAJPEAV?$list@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@utl@@@Z`
- size: `679`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x180004658`
- `0x180018c20`
- `0x18001b340`
- `0x180035c40`
- `0x180065a10`
- `0x18008b070`
- `0x18008b320`
- `0x180109924`
- `0x18012e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008b159`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008b1c2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008b202`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008b251`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008b2a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008b159`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008b1c2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008b202`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008b251`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008b2a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008b18b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008b18b`

## string_xrefs

- `0x18008b0b6`: `onecoreuap\base\appmodel\messagingom\utils\rcsserviceadapter\lib\rcsfiletransferserviceadapterimpl.cpp`
- `0x18008b1e2`: `onecoreuap\base\appmodel\messagingom\utils\rcsserviceadapter\lib\rcsfiletransferserviceadapterimpl.cpp`
- `0x18008b231`: `onecoreuap\base\appmodel\messagingom\utils\rcsserviceadapter\lib\rcsfiletransferserviceadapterimpl.cpp`
- `0x18008b28a`: `onecoreuap\base\appmodel\messagingom\utils\rcsserviceadapter\lib\rcsfiletransferserviceadapterimpl.cpp`
- `0x18008b2b2`: `onecoreuap\base\appmodel\messagingom\utils\rcsserviceadapter\lib\rcsfiletransferserviceadapterimpl.cpp`
- `0x18008b2d8`: `onecoreuap\base\appmodel\messagingom\utils\rcsserviceadapter\lib\rcsfiletransferserviceadapterimpl.cpp`

## pseudocode

```c
__int64 __fastcall RcsFileTransferServiceAdapterImpl::GetAllActiveFileTransfers(__int64 a1, __int64 a2)
{
  __int64 v4; // rcx
  int v5; // ebx
  __int64 v6; // rcx
  unsigned int i; // esi
  __int64 v9; // rcx
  int v10; // eax
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, HSTRING *); // rbx
  int v13; // eax
  PCWSTR StringRawBuffer; // rax
  __int64 v15; // rcx
  void (*v16)(void); // rax
  __int64 v17; // rcx
  __int64 v18; // [rsp+30h] [rbp-30h] BYREF
  _BYTE v19[40]; // [rsp+38h] [rbp-28h] BYREF
  unsigned int v20; // [rsp+90h] [rbp+30h] BYREF
  __int64 v21; // [rsp+A0h] [rbp+40h] BYREF
  HSTRING string; // [rsp+A8h] [rbp+48h] BYREF

  utl::list<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::allocator<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>::clear(a2);
  v4 = *(_QWORD *)(a1 + 8);
  v21 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v4 + 72LL))(v4, &v21);
  if ( v5 < 0 )
    goto LABEL_2;
  if ( v21 )
  {
    v20 = 0;
    v5 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v21 + 56LL))(v21, &v20);
    if ( v5 >= 0 )
    {
      for ( i = 0; ; ++i )
      {
        v9 = v21;
        if ( i >= v20 )
          goto LABEL_25;
        v18 = 0;
        v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v21 + 48LL))(v21, i, &v18);
        v5 = v10;
        if ( v10 < 0 )
          break;
        v11 = v18;
        string = 0;
        v12 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v18 + 80LL);
        WindowsDeleteString(0);
        string = 0;
        v13 = v12(v11, &string);
        v5 = v13;
        if ( v13 < 0 )
        {
          Log_HREvent_38(
            (unsigned int)v13,
            1,
            "onecoreuap\\base\\appmodel\\messagingom\\utils\\rcsserviceadapter\\lib\\rcsfiletransferserviceadapterimpl.cpp");
          WindowsDeleteString(string);
          string = 0;
          goto LABEL_23;
        }
        utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v19);
        StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
        if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                                 v19,
                                 StringRawBuffer) )
        {
          Log_HREvent_38(
            2147942414LL,
            0,
            "onecoreuap\\base\\appmodel\\messagingom\\utils\\rcsserviceadapter\\lib\\rcsfiletransferserviceadapterimpl.cpp");
          utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v19);
          WindowsDeleteString(string);
          string = 0;
          Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(&v18);
          v17 = v21;
          if ( v21 )
          {
            v21 = 0;
            v16 = *(void (**)(void))(*(_QWORD *)v17 + 16LL);
LABEL_19:
            v16();
          }
          return 2147942414LL;
        }
        if ( !(unsigned __int8)utl::list<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::allocator<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>::push_back(
                                 a2,
                                 v19) )
        {
          Log_HREvent_38(
            2147942414LL,
            0,
            "onecoreuap\\base\\appmodel\\messagingom\\utils\\rcsserviceadapter\\lib\\rcsfiletransferserviceadapterimpl.cpp");
          utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v19);
          WindowsDeleteString(string);
          string = 0;
          Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(&v18);
          v15 = v21;
          if ( v21 )
          {
            v21 = 0;
            v16 = *(void (**)(void))(*(_QWORD *)v15 + 16LL);
            goto LABEL_19;
          }
          return 2147942414LL;
        }
        utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v19);
        WindowsDeleteString(string);
        string = 0;
        Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(&v18);
      }
      Log_HREvent_38(
        (unsigned int)v10,
        1,
        "onecoreuap\\base\\appmodel\\messagingom\\utils\\rcsserviceadapter\\lib\\rcsfiletransferserviceadapterimpl.cpp");
LABEL_23:
      Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(&v18);
      goto LABEL_3;
    }
LABEL_2:
    Log_HREvent_38(
      (unsigned int)v5,
      1,
      "onecoreuap\\base\\appmodel\\messagingom\\utils\\rcsserviceadapter\\lib\\rcsfiletransferserviceadapterimpl.cpp");
LABEL_3:
    v6 = v21;
    if ( v21 )
    {
      v21 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    }
    return (unsigned int)v5;
  }
  Log_HREvent_38(
    0,
    0,
    "onecoreuap\\base\\appmodel\\messagingom\\utils\\rcsserviceadapter\\lib\\rcsfiletransferserviceadapterimpl.cpp");
  v9 = v21;
LABEL_25:
  if ( v9 )
  {
    v21 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  }
  return 0;
}

```

## disassembly

```asm
0x18008b070  mov     [rsp-28h+arg_8], rbx
0x18008b075  push    rbp
0x18008b076  push    rsi
0x18008b077  push    rdi
0x18008b078  push    r14
0x18008b07a  push    r15
0x18008b07c  mov     rbp, rsp
0x18008b07f  sub     rsp, 60h
0x18008b083  mov     rbx, rcx
0x18008b086  mov     r14, rdx
0x18008b089  mov     rcx, rdx
0x18008b08c  call    ?clear@?$list@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@utl@@QEAAXXZ; utl::list<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>>::clear(void)
0x18008b091  mov     rcx, [rbx+8]
0x18008b095  lea     rdx, [rbp+arg_10]
0x18008b099  xor     r15d, r15d
0x18008b09c  mov     [rbp+arg_10], r15
0x18008b0a0  mov     rax, [rcx]
0x18008b0a3  mov     rax, [rax+48h]
0x18008b0a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008b0ac  mov     ebx, eax
0x18008b0ae  test    eax, eax
0x18008b0b0  jns     short loc_18008B0E9
0x18008b0b2  lea     r9d, [r15+3Ch]
0x18008b0b6  lea     r8, aOnecoreuapBase_42; "onecoreuap\\base\\appmodel\\messagingom"...
0x18008b0bd  mov     edx, 1
0x18008b0c2  mov     ecx, ebx
0x18008b0c4  call    Log_HREvent_38
0x18008b0c9  mov     rcx, [rbp+arg_10]
0x18008b0cd  test    rcx, rcx
0x18008b0d0  jz      short loc_18008B0E2
0x18008b0d2  mov     [rbp+arg_10], r15
0x18008b0d6  mov     rax, [rcx]
0x18008b0d9  mov     rax, [rax+10h]
0x18008b0dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008b0e2  mov     eax, ebx
0x18008b0e4  jmp     loc_18008B303
0x18008b0e9  mov     rcx, [rbp+arg_10]
0x18008b0ed  test    rcx, rcx
0x18008b0f0  jz      loc_18008B2D2
0x18008b0f6  mov     [rbp+arg_0], r15d
0x18008b0fa  lea     rdx, [rbp+arg_0]
0x18008b0fe  mov     rax, [rcx]
0x18008b101  mov     rax, [rax+38h]
0x18008b105  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008b10a  mov     ebx, eax
0x18008b10c  test    eax, eax
0x18008b10e  jns     short loc_18008B118
0x18008b110  mov     r9d, 44h ; 'D'
0x18008b116  jmp     short loc_18008B0B6
0x18008b118  mov     esi, r15d
0x18008b11b  mov     rcx, [rbp+arg_10]
0x18008b11f  cmp     esi, [rbp+arg_0]
0x18008b122  jnb     loc_18008B2EC
0x18008b128  mov     [rbp+var_30], r15
0x18008b12c  lea     r8, [rbp+var_30]
0x18008b130  mov     rax, [rcx]
0x18008b133  mov     edx, esi
0x18008b135  mov     rax, [rax+30h]
0x18008b139  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008b13e  mov     ebx, eax
0x18008b140  test    eax, eax
0x18008b142  js      loc_18008B2AC
0x18008b148  mov     rdi, [rbp+var_30]
0x18008b14c  xor     ecx, ecx; string
0x18008b14e  mov     [rbp+string], r15
0x18008b152  mov     rax, [rdi]
0x18008b155  mov     rbx, [rax+50h]
0x18008b159  call    cs:__imp_WindowsDeleteString
0x18008b15f  lea     rdx, [rbp+string]
0x18008b163  mov     [rbp+string], r15
0x18008b167  mov     rcx, rdi
0x18008b16a  mov     rax, rbx
0x18008b16d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008b172  mov     ebx, eax
0x18008b174  test    eax, eax
0x18008b176  js      loc_18008B284
0x18008b17c  lea     rcx, [rbp+var_28]; void *
0x18008b180  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x18008b185  mov     rcx, [rbp+string]; string
0x18008b189  xor     edx, edx; length
0x18008b18b  call    cs:__imp_WindowsGetStringRawBuffer
0x18008b191  mov     rdx, rax
0x18008b194  lea     rcx, [rbp+var_28]
0x18008b198  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x18008b19d  test    al, al
0x18008b19f  jz      loc_18008B22B
0x18008b1a5  lea     rdx, [rbp+var_28]
0x18008b1a9  mov     rcx, r14
0x18008b1ac  call    ?push_back@?$list@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@utl@@QEAA_NAEBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@2@@Z; utl::list<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>>::push_back(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &)
0x18008b1b1  test    al, al
0x18008b1b3  jz      short loc_18008B1DC
0x18008b1b5  lea     rcx, [rbp+var_28]; void *
0x18008b1b9  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18008b1be  mov     rcx, [rbp+string]; string
0x18008b1c2  call    cs:__imp_WindowsDeleteString
0x18008b1c8  lea     rcx, [rbp+var_30]
0x18008b1cc  mov     [rbp+string], r15
0x18008b1d0  call    ?InternalRelease@?$ComPtr@U?$OperationCallback@PEAVAccount@Sync@Experiences@PhoneInternal@@@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(void)
0x18008b1d5  inc     esi
0x18008b1d7  jmp     loc_18008B11B
0x18008b1dc  mov     r9d, 50h ; 'P'
0x18008b1e2  lea     r8, aOnecoreuapBase_42; "onecoreuap\\base\\appmodel\\messagingom"...
0x18008b1e9  xor     edx, edx
0x18008b1eb  mov     ecx, 8007000Eh
0x18008b1f0  call    Log_HREvent_38
0x18008b1f5  lea     rcx, [rbp+var_28]; void *
0x18008b1f9  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18008b1fe  mov     rcx, [rbp+string]; string
0x18008b202  call    cs:__imp_WindowsDeleteString
0x18008b208  lea     rcx, [rbp+var_30]
0x18008b20c  mov     [rbp+string], r15
0x18008b210  call    ?InternalRelease@?$ComPtr@U?$OperationCallback@PEAVAccount@Sync@Experiences@PhoneInternal@@@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(void)
0x18008b215  mov     rcx, [rbp+arg_10]
0x18008b219  test    rcx, rcx
0x18008b21c  jz      short loc_18008B27D
0x18008b21e  mov     [rbp+arg_10], r15
0x18008b222  mov     rax, [rcx]
0x18008b225  mov     rax, [rax+10h]
0x18008b229  jmp     short loc_18008B278
0x18008b22b  mov     r9d, 4Eh ; 'N'
0x18008b231  lea     r8, aOnecoreuapBase_42; "onecoreuap\\base\\appmodel\\messagingom"...
0x18008b238  xor     edx, edx
0x18008b23a  mov     ecx, 8007000Eh
0x18008b23f  call    Log_HREvent_38
0x18008b244  lea     rcx, [rbp+var_28]; void *
0x18008b248  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18008b24d  mov     rcx, [rbp+string]; string
0x18008b251  call    cs:__imp_WindowsDeleteString
0x18008b257  lea     rcx, [rbp+var_30]
0x18008b25b  mov     [rbp+string], r15
0x18008b25f  call    ?InternalRelease@?$ComPtr@U?$OperationCallback@PEAVAccount@Sync@Experiences@PhoneInternal@@@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(void)
0x18008b264  mov     rcx, [rbp+arg_10]
0x18008b268  test    rcx, rcx
0x18008b26b  jz      short loc_18008B27D
0x18008b26d  mov     [rbp+arg_10], r15
0x18008b271  mov     rdx, [rcx]
0x18008b274  mov     rax, [rdx+10h]
0x18008b278  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008b27d  mov     eax, 8007000Eh
0x18008b282  jmp     short loc_18008B303
0x18008b284  mov     r9d, 4Bh ; 'K'
0x18008b28a  lea     r8, aOnecoreuapBase_42; "onecoreuap\\base\\appmodel\\messagingom"...
0x18008b291  mov     ecx, ebx
0x18008b293  lea     edx, [r9-4Ah]
0x18008b297  call    Log_HREvent_38
0x18008b29c  mov     rcx, [rbp+string]; string
0x18008b2a0  call    cs:__imp_WindowsDeleteString
0x18008b2a6  mov     [rbp+string], r15
0x18008b2aa  jmp     short loc_18008B2C4
0x18008b2ac  mov     r9d, 48h ; 'H'
0x18008b2b2  lea     r8, aOnecoreuapBase_42; "onecoreuap\\base\\appmodel\\messagingom"...
0x18008b2b9  mov     ecx, ebx
0x18008b2bb  lea     edx, [r9-47h]
0x18008b2bf  call    Log_HREvent_38
0x18008b2c4  lea     rcx, [rbp+var_30]
0x18008b2c8  call    ?InternalRelease@?$ComPtr@U?$OperationCallback@PEAVAccount@Sync@Experiences@PhoneInternal@@@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(void)
0x18008b2cd  jmp     loc_18008B0C9
0x18008b2d2  mov     r9d, 41h ; 'A'
0x18008b2d8  lea     r8, aOnecoreuapBase_42; "onecoreuap\\base\\appmodel\\messagingom"...
0x18008b2df  xor     edx, edx
0x18008b2e1  xor     ecx, ecx
0x18008b2e3  call    Log_HREvent_38
0x18008b2e8  mov     rcx, [rbp+arg_10]
0x18008b2ec  test    rcx, rcx
0x18008b2ef  jz      short loc_18008B301
0x18008b2f1  mov     [rbp+arg_10], r15
0x18008b2f5  mov     rax, [rcx]
0x18008b2f8  mov     rax, [rax+10h]
0x18008b2fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008b301  xor     eax, eax
0x18008b303  mov     rbx, [rsp+60h+arg_8]
0x18008b30b  add     rsp, 60h
0x18008b30f  pop     r15
0x18008b311  pop     r14
0x18008b313  pop     rdi
0x18008b314  pop     rsi
0x18008b315  pop     rbp
0x18008b316  retn
```
