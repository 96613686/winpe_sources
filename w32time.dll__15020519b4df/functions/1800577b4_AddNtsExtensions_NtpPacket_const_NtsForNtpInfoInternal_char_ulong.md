# AddNtsExtensions(NtpPacket const &,NtsForNtpInfoInternal &,char *,ulong *)

- ea: `0x1800577b4`
- end: `0x180057a06`
- name: `?AddNtsExtensions@@YAJAEBUNtpPacket@@AEAUNtsForNtpInfoInternal@@PEADPEAK@Z`
- size: `594`
- prototype: `__int64 __fastcall(const struct NtpPacket *, struct NtsForNtpInfoInternal *, char *, unsigned int *)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800556a4`

## callees

- `0x180018138`
- `0x18001d9a0`
- `0x18003b8fc`
- `0x18003d270`
- `0x180045abc`
- `0x180056920`
- `0x180057040`
- `0x180057498`
- `0x1800576cc`
- `0x1800577b4`
- `0x180057aa8`
- `0x180058150`

## string_xrefs

- `0x180057890`: `onecore\ds\security\services\w32time\nts\ntsextensions.cpp`
- `0x1800578d6`: `onecore\ds\security\services\w32time\nts\ntsextensions.cpp`
- `0x180057914`: `onecore\ds\security\services\w32time\nts\ntsextensions.cpp`
- `0x1800577ef`: `AddNtsExtensions: buffer is null\n`
- `0x180057864`: `AddNtsExtensions: Adding NTS extensions to packet with AEAD: %d. There are %d cookies remaining.\n`
- `0x1800579c2`: `AddNtsExtensions: Saved unique Id: %s\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall AddNtsExtensions(
        const struct NtpPacket *a1,
        struct NtsForNtpInfoInternal *a2,
        char *a3,
        unsigned int *a4)
{
  const char *v7; // r9
  __int64 result; // rax
  int v9; // eax
  unsigned int v10; // edi
  int v11; // eax
  unsigned int v12; // edi
  int v13; // eax
  unsigned int v14; // edi
  _QWORD *v15; // rax
  unsigned int v16; // [rsp+20h] [rbp-88h] BYREF
  __int64 v17; // [rsp+28h] [rbp-80h] BYREF
  char v18; // [rsp+30h] [rbp-78h]
  __int64 v19; // [rsp+38h] [rbp-70h]
  __int128 v20; // [rsp+40h] [rbp-68h] BYREF
  __int128 v21; // [rsp+50h] [rbp-58h]
  __int64 v22; // [rsp+60h] [rbp-48h] BYREF
  char v23; // [rsp+68h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  try
  {
    if ( a3 )
    {
      v16 = 0;
      *(_OWORD *)a3 = *(_OWORD *)a1;
      *((_OWORD *)a3 + 1) = *((_OWORD *)a1 + 1);
      *((_OWORD *)a3 + 2) = *((_OWORD *)a1 + 2);
      v16 = 48;
      if ( (unsigned __int8)FileLogAllowEntry(200) )
        FileLogAdd(
          L"AddNtsExtensions: Adding NTS extensions to packet with AEAD: %d. There are %d cookies remaining.\n",
          *((unsigned __int16 *)a2 + 86),
          0xAAAAAAAAAAAAAAABuLL * ((__int64)(*((_QWORD *)a2 + 28) - *((_QWORD *)a2 + 27)) >> 3));
      v9 = AddUniqueIdentifierExtensionField(a3, 0x30u, &v16);
      v10 = v9;
      if ( v9 >= 0 )
      {
        v11 = AddCookieExtensionField(*((_QWORD *)a2 + 28) - 24LL, a3, v16, &v16);
        v12 = v11;
        if ( v11 >= 0 )
        {
          v13 = AddAEExtensionFields(a2, a3, v16, &v16);
          v14 = v13;
          if ( v13 >= 0 )
          {
            *a4 = v16;
            std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(*((_QWORD *)a2 + 28) - 24LL);
            *((_QWORD *)a2 + 28) -= 24LL;
            v20 = 0;
            v21 = 0;
            v20 = *(_OWORD *)(a3 + 52);
            v21 = *(_OWORD *)(a3 + 68);
            std::_Tree<std::_Tset_traits<std::array<unsigned char,32>,std::less<std::array<unsigned char,32>>,std::allocator<std::array<unsigned char,32>>,0>>::_Emplace<std::array<unsigned char,32> const &>(
              (char *)a2 + 240,
              &v17,
              &v20);
            v19 = v17;
            v22 = v17;
            v23 = v18;
            if ( (unsigned __int8)FileLogAllowEntry(200) )
            {
              v15 = (_QWORD *)UniqueIdToString(&v22, &v20);
              if ( v15[3] > 7u )
                v15 = (_QWORD *)*v15;
              FileLogAdd(L"AddNtsExtensions: Saved unique Id: %s\n", v15);
              std::wstring::~wstring((__int64)&v22);
            }
            result = 0;
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xD7,
              (unsigned int)"onecore\\ds\\security\\services\\w32time\\nts\\ntsextensions.cpp",
              (const char *)(unsigned int)v13,
              v16);
            result = v14;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xD6,
            (unsigned int)"onecore\\ds\\security\\services\\w32time\\nts\\ntsextensions.cpp",
            (const char *)(unsigned int)v11,
            v16);
          result = v12;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xD5,
          (unsigned int)"onecore\\ds\\security\\services\\w32time\\nts\\ntsextensions.cpp",
          (const char *)(unsigned int)v9,
          v16);
        result = v10;
      }
    }
    else
    {
      if ( (unsigned __int8)FileLogAllowEntry(0) )
        FileLogAdd(L"AddNtsExtensions: buffer is null\n");
      result = 2147942487LL;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xE3,
                           (unsigned int)"onecore\\ds\\security\\services\\w32time\\nts\\ntsextensions.cpp",
                           v7);
  }
  return result;
}

```

## disassembly

```asm
0x1800577b4  mov     [rsp+arg_0], rbx
0x1800577b9  push    rsi
0x1800577ba  push    rdi
0x1800577bb  push    r14
0x1800577bd  sub     rsp, 90h
0x1800577c4  mov     rax, cs:__security_cookie
0x1800577cb  xor     rax, rsp
0x1800577ce  mov     [rsp+0A8h+var_28], rax
0x1800577d6  mov     r14, r9
0x1800577d9  mov     rbx, r8
0x1800577dc  mov     rsi, rdx
0x1800577df  test    rbx, rbx
0x1800577e2  jnz     short loc_180057805
0x1800577e4  xor     ecx, ecx
0x1800577e6  call    FileLogAllowEntry
0x1800577eb  test    al, al
0x1800577ed  jz      short loc_1800577FB
0x1800577ef  lea     rcx, aAddntsextensio_0; "AddNtsExtensions: buffer is null\n"
0x1800577f6  call    FileLogAdd
0x1800577fb  mov     eax, 80070057h
0x180057800  jmp     loc_1800579E1
0x180057805  mov     [rsp+0A8h+var_88], 0
0x18005780d  movups  xmm0, xmmword ptr [rcx]
0x180057810  movups  xmmword ptr [r8], xmm0
0x180057814  movups  xmm1, xmmword ptr [rcx+10h]
0x180057818  movups  xmmword ptr [r8+10h], xmm1
0x18005781d  movups  xmm0, xmmword ptr [rcx+20h]
0x180057821  movups  xmmword ptr [r8+20h], xmm0
0x180057826  mov     edi, 30h ; '0'
0x18005782b  mov     [rsp+0A8h+var_88], edi; int
0x18005782f  mov     ecx, 0C8h
0x180057834  call    FileLogAllowEntry
0x180057839  test    al, al
0x18005783b  jz      short loc_180057870
0x18005783d  mov     r8, [rsi+0E0h]
0x180057844  sub     r8, [rsi+0D8h]
0x18005784b  sar     r8, 3
0x18005784f  mov     rax, 0AAAAAAAAAAAAAAABh
0x180057859  imul    r8, rax
0x18005785d  movzx   edx, word ptr [rsi+0ACh]
0x180057864  lea     rcx, aAddntsextensio_1; "AddNtsExtensions: Adding NTS extensions"...
0x18005786b  call    FileLogAdd
0x180057870  lea     r8, [rsp+0A8h+var_88]; unsigned int *
0x180057875  mov     edx, edi; unsigned int
0x180057877  mov     rcx, rbx; void *
0x18005787a  call    ?AddUniqueIdentifierExtensionField@@YAJPEAXKPEAK@Z; AddUniqueIdentifierExtensionField(void *,ulong,ulong *)
0x18005787f  mov     edi, eax
0x180057881  test    eax, eax
0x180057883  jns     short loc_1800578A8
0x180057885  mov     rcx, [rsp+0A8h]; this
0x18005788d  mov     r9d, eax; char *
0x180057890  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\services\\w32tim"...
0x180057897  mov     edx, 0D5h; void *
0x18005789c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800578a1  mov     eax, edi
0x1800578a3  jmp     loc_1800579E1
0x1800578a8  mov     rcx, [rsi+0E0h]
0x1800578af  sub     rcx, 18h
0x1800578b3  lea     r9, [rsp+0A8h+var_88]
0x1800578b8  mov     r8d, [rsp+0A8h+var_88]
0x1800578bd  mov     rdx, rbx
0x1800578c0  call    ?AddCookieExtensionField@@YAJAEBV?$vector@EU?$secure_allocator@E@wil@@@std@@PEAXKPEAK@Z; AddCookieExtensionField(std::vector<uchar,wil::secure_allocator<uchar>> const &,void *,ulong,ulong *)
0x1800578c5  mov     edi, eax
0x1800578c7  test    eax, eax
0x1800578c9  jns     short loc_1800578EE
0x1800578cb  mov     rcx, [rsp+0A8h]; this
0x1800578d3  mov     r9d, eax; char *
0x1800578d6  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\services\\w32tim"...
0x1800578dd  mov     edx, 0D6h; void *
0x1800578e2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800578e7  mov     eax, edi
0x1800578e9  jmp     loc_1800579E1
0x1800578ee  lea     r9, [rsp+0A8h+var_88]; unsigned int *
0x1800578f3  mov     r8d, [rsp+0A8h+var_88]; unsigned int
0x1800578f8  mov     rdx, rbx; void *
0x1800578fb  mov     rcx, rsi; struct NtsForNtpInfoInternal *
0x1800578fe  call    ?AddAEExtensionFields@@YAJAEAUNtsForNtpInfoInternal@@PEAXKPEAK@Z; AddAEExtensionFields(NtsForNtpInfoInternal &,void *,ulong,ulong *)
0x180057903  mov     edi, eax
0x180057905  test    eax, eax
0x180057907  jns     short loc_18005792C
0x180057909  mov     rcx, [rsp+0A8h]; this
0x180057911  mov     r9d, eax; char *
0x180057914  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\services\\w32tim"...
0x18005791b  mov     edx, 0D7h; void *
0x180057920  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180057925  mov     eax, edi
0x180057927  jmp     loc_1800579E1
0x18005792c  mov     eax, [rsp+0A8h+var_88]
0x180057930  mov     [r14], eax
0x180057933  mov     rcx, [rsi+0E0h]
0x18005793a  sub     rcx, 18h
0x18005793e  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
0x180057943  add     qword ptr [rsi+0E0h], 0FFFFFFFFFFFFFFE8h
0x18005794b  xorps   xmm0, xmm0
0x18005794e  movups  [rsp+0A8h+var_68], xmm0
0x180057953  movups  [rsp+0A8h+var_58], xmm0
0x180057958  movups  xmm0, xmmword ptr [rbx+34h]
0x18005795c  movups  [rsp+0A8h+var_68], xmm0
0x180057961  movups  xmm1, xmmword ptr [rbx+44h]
0x180057965  movups  [rsp+0A8h+var_58], xmm1
0x18005796a  lea     rcx, [rsi+0F0h]
0x180057971  lea     r8, [rsp+0A8h+var_68]
0x180057976  lea     rdx, [rsp+0A8h+var_80]
0x18005797b  call    ??$_Emplace@AEBV?$array@E$0CA@@std@@@?$_Tree@V?$_Tset_traits@V?$array@E$0CA@@std@@U?$less@V?$array@E$0CA@@std@@@2@V?$allocator@V?$array@E$0CA@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@V?$array@E$0CA@@std@@PEAX@std@@_N@1@AEBV?$array@E$0CA@@1@@Z; std::_Tree<std::_Tset_traits<std::array<uchar,32>,std::less<std::array<uchar,32>>,std::allocator<std::array<uchar,32>>,0>>::_Emplace<std::array<uchar,32> const &>(std::array<uchar,32> const &)
0x180057980  mov     rax, [rsp+0A8h+var_80]
0x180057985  mov     [rsp+0A8h+var_70], rax
0x18005798a  mov     [rsp+0A8h+var_48], rax
0x18005798f  mov     al, [rsp+0A8h+var_78]
0x180057993  mov     [rsp+0A8h+var_40], al
0x180057997  mov     ecx, 0C8h
0x18005799c  call    FileLogAllowEntry
0x1800579a1  test    al, al
0x1800579a3  jz      short loc_1800579D9
0x1800579a5  lea     rdx, [rsp+0A8h+var_68]
0x1800579aa  lea     rcx, [rsp+0A8h+var_48]
0x1800579af  call    ?UniqueIdToString@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$array@E$0CA@@2@@Z; UniqueIdToString(std::array<uchar,32> const &)
0x1800579b4  nop
0x1800579b5  cmp     qword ptr [rax+18h], 7
0x1800579ba  jbe     short loc_1800579BF
0x1800579bc  mov     rax, [rax]
0x1800579bf  mov     rdx, rax
0x1800579c2  lea     rcx, aAddntsextensio; "AddNtsExtensions: Saved unique Id: %s\n"
0x1800579c9  call    FileLogAdd
0x1800579ce  nop
0x1800579cf  lea     rcx, [rsp+0A8h+var_48]
0x1800579d4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800579d9  xor     eax, eax
0x1800579db  jmp     short loc_1800579E1
0x1800579dd  mov     eax, [rsp+0A8h+var_88]
0x1800579e1  mov     rcx, [rsp+0A8h+var_28]
0x1800579e9  xor     rcx, rsp; StackCookie
0x1800579ec  call    __security_check_cookie
0x1800579f1  mov     rbx, [rsp+0A8h+arg_0]
0x1800579f9  add     rsp, 90h
0x180057a00  pop     r14
0x180057a02  pop     rdi
0x180057a03  pop     rsi
0x180057a04  retn
```
