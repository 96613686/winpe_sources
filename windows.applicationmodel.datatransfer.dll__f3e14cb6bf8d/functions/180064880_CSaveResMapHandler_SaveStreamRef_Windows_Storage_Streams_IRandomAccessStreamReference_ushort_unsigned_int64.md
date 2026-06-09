# CSaveResMapHandler::_SaveStreamRef(Windows::Storage::Streams::IRandomAccessStreamReference *,ushort *,unsigned __int64)

- ea: `0x180064880`
- end: `0x180064b98`
- name: `?_SaveStreamRef@CSaveResMapHandler@@AEAAJPEAUIRandomAccessStreamReference@Streams@Storage@Windows@@PEAG_K@Z`
- size: `792`
- prototype: `__int64 __fastcall(CSaveResMapHandler *__hidden this, struct Windows::Storage::Streams::IRandomAccessStreamReference *, unsigned __int16 *, unsigned __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180062f30`

## callees

- `0x180002ad0`
- `0x18000346c`
- `0x180008b68`
- `0x18004eabc`
- `0x18006423c`
- `0x180064880`
- `0x180064ba0`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800649e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800649e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800649ba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800649ba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x1800649a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x1800649a6`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall CSaveResMapHandler::_SaveStreamRef(
        CSaveResMapHandler *this,
        struct Windows::Storage::Streams::IRandomAccessStreamReference *a2,
        unsigned __int16 *a3)
{
  int UniqueTempFileName; // ebx
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, GUID *, __int64); // rbx
  __int64 v8; // rax
  const unsigned __int16 *StringRawBuffer; // rax
  unsigned __int64 v10; // rcx
  struct Windows::Storage::Streams::IInputStream *v11; // rcx
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, GUID *, __int64); // rbx
  __int64 v14; // rax
  struct Windows::Storage::Streams::IInputStream *v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  struct Windows::Storage::Streams::IInputStream *v19; // [rsp+20h] [rbp-E0h] BYREF
  BOOL hasEmbedNull[2]; // [rsp+28h] [rbp-D8h] BYREF
  unsigned __int64 v21; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v22; // [rsp+38h] [rbp-C8h] BYREF
  int v23; // [rsp+40h] [rbp-C0h] BYREF
  HSTRING string; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 v25[264]; // [rsp+50h] [rbp-B0h] BYREF

  *a3 = 0;
  v22 = 0;
  UniqueTempFileName = (**(__int64 (__fastcall ***)(struct Windows::Storage::Streams::IRandomAccessStreamReference *, GUID *, __int64 *))a2)(
                         a2,
                         &GUID_3fe8e0e3_eb50_4682_b91d_21028012a049,
                         &v22);
  if ( UniqueTempFileName >= 0 )
  {
    v23 = 0;
    UniqueTempFileName = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v22 + 24LL))(v22, &v23);
    if ( UniqueTempFileName >= 0 )
    {
      if ( v23 == 1 )
      {
        v19 = 0;
        v6 = v22;
        v7 = *(__int64 (__fastcall **)(__int64, GUID *, __int64))(*(_QWORD *)v22 + 32LL);
        v8 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>(&v19);
        UniqueTempFileName = v7(v6, &GUID_fa3f6186_4214_428c_a64c_14c9ac7315ea, v8);
        if ( UniqueTempFileName >= 0 )
        {
          v21 = 0;
          UniqueTempFileName = (**(__int64 (__fastcall ***)(struct Windows::Storage::Streams::IInputStream *, GUID *, unsigned __int64 *))v19)(
                                 v19,
                                 &GUID_4207a996_ca2f_42f7_bde8_8b10457a7f30,
                                 &v21);
          if ( UniqueTempFileName >= 0 )
          {
            string = 0;
            UniqueTempFileName = (*(__int64 (__fastcall **)(unsigned __int64, HSTRING *))(*(_QWORD *)v21 + 96LL))(
                                   v21,
                                   &string);
            if ( UniqueTempFileName >= 0 )
            {
              hasEmbedNull[0] = 0;
              WindowsStringHasEmbeddedNull(string, hasEmbedNull);
              if ( hasEmbedNull[0] )
              {
                UniqueTempFileName = -2147024809;
              }
              else
              {
                StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
                UniqueTempFileName = StringCchCopyW(a3, 0x104u, StringRawBuffer);
              }
            }
            if ( string )
              WindowsDeleteString(string);
          }
          v10 = v21;
          if ( v21 )
          {
            v21 = 0;
            (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v10 + 16LL))(v10);
          }
        }
        v11 = v19;
        if ( v19 )
        {
          v19 = 0;
          (*(void (__fastcall **)(struct Windows::Storage::Streams::IInputStream *))(*(_QWORD *)v11 + 16LL))(v11);
        }
      }
      else
      {
        *((_BYTE *)this + 568) = 0;
        memset_0(v25, 0, 0x208u);
        UniqueTempFileName = CSaveResMapHandler::_GetUniqueTempFileName((const WCHAR *)this, v25);
        if ( UniqueTempFileName >= 0 )
        {
          *(_QWORD *)hasEmbedNull = 0;
          v12 = v22;
          v13 = *(__int64 (__fastcall **)(__int64, GUID *, __int64))(*(_QWORD *)v22 + 48LL);
          v14 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>(hasEmbedNull);
          UniqueTempFileName = v13(v12, &GUID_905a0fe1_bc53_11df_8c49_001e4fc686da, v14);
          if ( UniqueTempFileName >= 0 )
          {
            v21 = 0;
            UniqueTempFileName = (*(__int64 (__fastcall **)(_QWORD, unsigned __int64 *))(**(_QWORD **)hasEmbedNull + 48LL))(
                                   *(_QWORD *)hasEmbedNull,
                                   &v21);
            if ( UniqueTempFileName >= 0 )
            {
              if ( v21 <= 0x1400000 )
              {
                v19 = 0;
                UniqueTempFileName = (*(__int64 (__fastcall **)(_QWORD, _QWORD, struct Windows::Storage::Streams::IInputStream **))(**(_QWORD **)hasEmbedNull + 64LL))(
                                       *(_QWORD *)hasEmbedNull,
                                       0,
                                       &v19);
                if ( UniqueTempFileName >= 0 )
                {
                  UniqueTempFileName = CSaveResMapHandler::_SaveStreamToFile(this, v25, v19, v21);
                  if ( UniqueTempFileName >= 0 )
                    UniqueTempFileName = StringCchCopyW(a3, 0x104u, v25);
                }
                v15 = v19;
                if ( v19 )
                {
                  v19 = 0;
                  (*(void (__fastcall **)(struct Windows::Storage::Streams::IInputStream *))(*(_QWORD *)v15 + 16LL))(v15);
                }
              }
              else
              {
                UniqueTempFileName = -2147483637;
              }
            }
          }
          v16 = *(_QWORD *)hasEmbedNull;
          if ( *(_QWORD *)hasEmbedNull )
          {
            *(_QWORD *)hasEmbedNull = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
          }
        }
      }
    }
  }
  v17 = v22;
  if ( v22 )
  {
    v22 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  }
  return (unsigned int)UniqueTempFileName;
}

```

## disassembly

```asm
0x180064880  mov     [rsp-8+arg_18], rbx
0x180064885  push    rbp
0x180064886  push    rsi
0x180064887  push    rdi
0x180064888  push    r14
0x18006488a  push    r15
0x18006488c  lea     rbp, [rsp-170h]
0x180064894  sub     rsp, 270h
0x18006489b  mov     rax, cs:__security_cookie
0x1800648a2  xor     rax, rsp
0x1800648a5  mov     [rbp+190h+var_30], rax
0x1800648ac  mov     r14, r8
0x1800648af  mov     r9, rdx
0x1800648b2  mov     rsi, rcx
0x1800648b5  xor     r15d, r15d
0x1800648b8  mov     [r8], r15w
0x1800648bc  mov     [rsp+290h+var_258], r15
0x1800648c1  mov     rax, [rdx]
0x1800648c4  lea     r8, [rsp+290h+var_258]
0x1800648c9  lea     rdx, _GUID_3fe8e0e3_eb50_4682_b91d_21028012a049
0x1800648d0  mov     rcx, r9
0x1800648d3  mov     rax, [rax]
0x1800648d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800648db  mov     ebx, eax
0x1800648dd  test    eax, eax
0x1800648df  js      loc_180064B54
0x1800648e5  mov     [rsp+290h+var_250], r15d
0x1800648ea  mov     rcx, [rsp+290h+var_258]
0x1800648ef  mov     rax, [rcx]
0x1800648f2  lea     rdx, [rsp+290h+var_250]
0x1800648f7  mov     rax, [rax+18h]
0x1800648fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064900  mov     ebx, eax
0x180064902  test    eax, eax
0x180064904  js      loc_180064B54
0x18006490a  cmp     [rsp+290h+var_250], 1
0x18006490f  jnz     loc_180064A27
0x180064915  mov     [rsp+290h+var_270], r15
0x18006491a  mov     rdi, [rsp+290h+var_258]
0x18006491f  mov     rax, [rdi]
0x180064922  mov     rbx, [rax+20h]
0x180064926  lea     rcx, [rsp+290h+var_270]
0x18006492b  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>)
0x180064930  mov     r8, rax
0x180064933  lea     rdx, _GUID_fa3f6186_4214_428c_a64c_14c9ac7315ea
0x18006493a  mov     rcx, rdi
0x18006493d  mov     rax, rbx
0x180064940  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064945  mov     ebx, eax
0x180064947  test    eax, eax
0x180064949  js      loc_180064A06
0x18006494f  mov     [rsp+290h+var_260], r15
0x180064954  mov     rcx, [rsp+290h+var_270]
0x180064959  mov     rax, [rcx]
0x18006495c  lea     r8, [rsp+290h+var_260]
0x180064961  lea     rdx, _GUID_4207a996_ca2f_42f7_bde8_8b10457a7f30
0x180064968  mov     rax, [rax]
0x18006496b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064970  mov     ebx, eax
0x180064972  test    eax, eax
0x180064974  js      short loc_1800649EA
0x180064976  mov     [rsp+290h+string], r15
0x18006497b  mov     rcx, [rsp+290h+var_260]
0x180064980  mov     rax, [rcx]
0x180064983  lea     rdx, [rsp+290h+string]
0x180064988  mov     rax, [rax+60h]
0x18006498c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064991  mov     ebx, eax
0x180064993  test    eax, eax
0x180064995  js      short loc_1800649D9
0x180064997  mov     [rsp+290h+hasEmbedNull], r15d
0x18006499c  lea     rdx, [rsp+290h+hasEmbedNull]; hasEmbedNull
0x1800649a1  mov     rcx, [rsp+290h+string]; string
0x1800649a6  call    cs:__imp_WindowsStringHasEmbeddedNull
0x1800649ac  cmp     [rsp+290h+hasEmbedNull], r15d
0x1800649b1  jnz     short loc_1800649D4
0x1800649b3  xor     edx, edx; length
0x1800649b5  mov     rcx, [rsp+290h+string]; string
0x1800649ba  call    cs:__imp_WindowsGetStringRawBuffer
0x1800649c0  mov     r8, rax; unsigned __int16 *
0x1800649c3  mov     edx, 104h; unsigned __int64
0x1800649c8  mov     rcx, r14; unsigned __int16 *
0x1800649cb  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800649d0  mov     ebx, eax
0x1800649d2  jmp     short loc_1800649D9
0x1800649d4  mov     ebx, 80070057h
0x1800649d9  mov     rcx, [rsp+290h+string]; string
0x1800649de  test    rcx, rcx
0x1800649e1  jz      short loc_1800649EA
0x1800649e3  call    cs:__imp_WindowsDeleteString
0x1800649e9  nop
0x1800649ea  mov     rcx, [rsp+290h+var_260]
0x1800649ef  test    rcx, rcx
0x1800649f2  jz      short loc_180064A06
0x1800649f4  mov     [rsp+290h+var_260], r15
0x1800649f9  mov     rax, [rcx]
0x1800649fc  mov     rax, [rax+10h]
0x180064a00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064a05  nop
0x180064a06  mov     rcx, [rsp+290h+var_270]
0x180064a0b  test    rcx, rcx
0x180064a0e  jz      short loc_180064A22
0x180064a10  mov     [rsp+290h+var_270], r15
0x180064a15  mov     rax, [rcx]
0x180064a18  mov     rax, [rax+10h]
0x180064a1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064a21  nop
0x180064a22  jmp     loc_180064B54
0x180064a27  mov     [rsi+238h], r15b
0x180064a2e  xor     edx, edx; Val
0x180064a30  mov     r8d, 208h; Size
0x180064a36  lea     rcx, [rsp+290h+var_240]; void *
0x180064a3b  call    memset_0
0x180064a40  lea     rdx, [rsp+290h+var_240]; unsigned __int16 *
0x180064a45  mov     rcx, rsi; this
0x180064a48  call    ?_GetUniqueTempFileName@CSaveResMapHandler@@AEAAJPEAG_K@Z; CSaveResMapHandler::_GetUniqueTempFileName(ushort *,unsigned __int64)
0x180064a4d  mov     ebx, eax
0x180064a4f  test    eax, eax
0x180064a51  js      loc_180064B54
0x180064a57  mov     qword ptr [rsp+290h+hasEmbedNull], r15
0x180064a5c  mov     rdi, [rsp+290h+var_258]
0x180064a61  mov     rax, [rdi]
0x180064a64  mov     rbx, [rax+30h]
0x180064a68  lea     rcx, [rsp+290h+hasEmbedNull]
0x180064a6d  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>)
0x180064a72  mov     r8, rax
0x180064a75  lea     rdx, _GUID_905a0fe1_bc53_11df_8c49_001e4fc686da
0x180064a7c  mov     rcx, rdi
0x180064a7f  mov     rax, rbx
0x180064a82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064a87  mov     ebx, eax
0x180064a89  test    eax, eax
0x180064a8b  js      loc_180064B38
0x180064a91  mov     [rsp+290h+var_260], r15
0x180064a96  mov     rcx, qword ptr [rsp+290h+hasEmbedNull]
0x180064a9b  mov     rax, [rcx]
0x180064a9e  lea     rdx, [rsp+290h+var_260]
0x180064aa3  mov     rax, [rax+30h]
0x180064aa7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064aac  mov     ebx, eax
0x180064aae  test    eax, eax
0x180064ab0  js      loc_180064B38
0x180064ab6  cmp     [rsp+290h+var_260], 1400000h
0x180064abf  jbe     short loc_180064AC8
0x180064ac1  mov     ebx, 8000000Bh
0x180064ac6  jmp     short loc_180064B38
0x180064ac8  mov     [rsp+290h+var_270], r15
0x180064acd  mov     rcx, qword ptr [rsp+290h+hasEmbedNull]
0x180064ad2  mov     rax, [rcx]
0x180064ad5  lea     r8, [rsp+290h+var_270]
0x180064ada  xor     edx, edx
0x180064adc  mov     rax, [rax+40h]
0x180064ae0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064ae5  mov     ebx, eax
0x180064ae7  test    eax, eax
0x180064ae9  js      short loc_180064B1C
0x180064aeb  mov     r9, [rsp+290h+var_260]; unsigned __int64
0x180064af0  mov     r8, [rsp+290h+var_270]; struct Windows::Storage::Streams::IInputStream *
0x180064af5  lea     rdx, [rsp+290h+var_240]; unsigned __int16 *
0x180064afa  mov     rcx, rsi; this
0x180064afd  call    ?_SaveStreamToFile@CSaveResMapHandler@@AEAAJPEBGPEAUIInputStream@Streams@Storage@Windows@@_K@Z; CSaveResMapHandler::_SaveStreamToFile(ushort const *,Windows::Storage::Streams::IInputStream *,unsigned __int64)
0x180064b02  mov     ebx, eax
0x180064b04  test    eax, eax
0x180064b06  js      short loc_180064B1C
0x180064b08  lea     r8, [rsp+290h+var_240]; unsigned __int16 *
0x180064b0d  mov     edx, 104h; unsigned __int64
0x180064b12  mov     rcx, r14; unsigned __int16 *
0x180064b15  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180064b1a  mov     ebx, eax
0x180064b1c  mov     rcx, [rsp+290h+var_270]
0x180064b21  test    rcx, rcx
0x180064b24  jz      short loc_180064B38
0x180064b26  mov     [rsp+290h+var_270], r15
0x180064b2b  mov     rax, [rcx]
0x180064b2e  mov     rax, [rax+10h]
0x180064b32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064b37  nop
0x180064b38  mov     rcx, qword ptr [rsp+290h+hasEmbedNull]
0x180064b3d  test    rcx, rcx
0x180064b40  jz      short loc_180064B54
0x180064b42  mov     qword ptr [rsp+290h+hasEmbedNull], r15
0x180064b47  mov     rax, [rcx]
0x180064b4a  mov     rax, [rax+10h]
0x180064b4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064b53  nop
0x180064b54  mov     rcx, [rsp+290h+var_258]
0x180064b59  test    rcx, rcx
0x180064b5c  jz      short loc_180064B70
0x180064b5e  mov     [rsp+290h+var_258], r15
0x180064b63  mov     rax, [rcx]
0x180064b66  mov     rax, [rax+10h]
0x180064b6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064b6f  nop
0x180064b70  mov     eax, ebx
0x180064b72  mov     rcx, [rbp+190h+var_30]
0x180064b79  xor     rcx, rsp; StackCookie
0x180064b7c  call    __security_check_cookie
0x180064b81  mov     rbx, [rsp+290h+arg_18]
0x180064b89  add     rsp, 270h
0x180064b90  pop     r15
0x180064b92  pop     r14
0x180064b94  pop     rdi
0x180064b95  pop     rsi
0x180064b96  pop     rbp
0x180064b97  retn
```
