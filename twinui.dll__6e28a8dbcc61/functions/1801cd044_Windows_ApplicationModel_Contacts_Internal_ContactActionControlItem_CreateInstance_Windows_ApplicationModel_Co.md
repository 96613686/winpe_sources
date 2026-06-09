# Windows::ApplicationModel::Contacts::Internal::ContactActionControlItem_CreateInstance(Windows::ApplicationModel::Contacts::IContact2 *,HSTRING__ *,HSTRING__ *,Windows::ApplicationModel::Contacts::Internal::IContactActionControlItem * *)

- ea: `0x1801cd044`
- end: `0x1801cd3c3`
- name: `?ContactActionControlItem_CreateInstance@Internal@Contacts@ApplicationModel@Windows@@YAJPEAUIContact2@234@PEAUHSTRING__@@1PEAPEAUIContactActionControlItem@1234@@Z`
- size: `895`
- prototype: `int(Windows::ApplicationModel::Contacts::Internal *__hidden this, struct Windows::ApplicationModel::Contacts::IContact2 *, HSTRING, HSTRING, struct Windows::ApplicationModel::Contacts::Internal::IContactActionControlItem **)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1801c26a0`

## callees

- `0x18000b7e8`
- `0x18000c350`
- `0x18013d330`
- `0x1801cafd8`
- `0x1801cd044`
- `0x1801cd3cc`
- `0x1801d80c8`
- `0x1801d8164`
- `0x1801d84f0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801cd0d2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801cd0d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801cd11f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801cd130`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801cd1ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801cd1f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801cd2b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801cd379`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801cd11f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801cd130`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801cd1ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801cd1f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801cd2b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801cd379`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801cd090`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801cd090`

## pseudocode

```c
__int64 __fastcall Windows::ApplicationModel::Contacts::Internal::ContactActionControlItem_CreateInstance(
        Windows::ApplicationModel::Contacts::Internal *this,
        struct Windows::ApplicationModel::Contacts::IContact2 *a2,
        HSTRING a3,
        void **a4)
{
  struct Windows::ApplicationModel::Contacts::IContact2 *v4; // rdi
  const WCHAR *StringRawBuffer; // rax
  char v7; // r12
  int Instance; // esi
  __int64 v9; // r14
  unsigned int v10; // r15d
  HSTRING *v11; // r9
  int v12; // eax
  HSTRING v13; // rbx
  HSTRING v14; // rdi
  __int64 v15; // rsi
  struct Windows::ApplicationModel::Contacts::IContactAddress **v16; // r8
  HSTRING *v17; // r8
  __int64 v18; // rdi
  HSTRING v19; // rsi
  __int64 v20; // rbx
  HSTRING v22; // [rsp+50h] [rbp-B0h] BYREF
  UINT32 length; // [rsp+58h] [rbp-A8h] BYREF
  HSTRING string; // [rsp+60h] [rbp-A0h] BYREF
  void **v25; // [rsp+68h] [rbp-98h]
  Windows::ApplicationModel::Contacts::Internal *v26; // [rsp+70h] [rbp-90h]
  struct Windows::ApplicationModel::Contacts::IContact2 *v27; // [rsp+78h] [rbp-88h]
  __int64 v28; // [rsp+80h] [rbp-80h] BYREF
  __int64 v29[4]; // [rsp+88h] [rbp-78h] BYREF
  const WCHAR *v30; // [rsp+A8h] [rbp-58h]
  HSTRING_HEADER v31; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v32; // [rsp+C8h] [rbp-38h]
  HSTRING_HEADER v33; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v34; // [rsp+E8h] [rbp-18h]
  HSTRING_HEADER hstringHeader; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v36; // [rsp+108h] [rbp+8h]

  v4 = a2;
  v27 = a2;
  v26 = this;
  v25 = a4;
  length = 0;
  StringRawBuffer = WindowsGetStringRawBuffer((HSTRING)a2, &length);
  v30 = StringRawBuffer;
  v7 = 0;
  Instance = -2147024809;
  v9 = 0;
  while ( !v7 )
  {
    if ( CompareStringOrdinal(StringRawBuffer, length, (&off_1803E1770)[2 * v9], -1, 1) == 2 )
    {
      v7 = 1;
      v10 = *((_DWORD *)&off_1803E1770 + 4 * v9 + 2);
      if ( v10 < 2 )
        goto LABEL_8;
      if ( v10 == 2 )
      {
        v22 = 0;
        WindowsDeleteString(0);
        v22 = 0;
        Instance = Windows::ApplicationModel::Contacts::Internal::DeserializeEmailActivationContext(
                     a3,
                     (HSTRING)&v22,
                     v17);
        if ( Instance >= 0 )
        {
          v32 = 0;
          Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v31, &pszDefault, 1u, 0);
          v18 = v32;
          v19 = v22;
          v34 = 0;
          Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v33, &pszDefault, 1u, 0);
          v20 = v34;
          v36 = 0;
          Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, &pszDefault, 1u, 0);
          Instance = Windows::ApplicationModel::Contacts::Internal::ContactActionControlItem_CreateInstance(
                       2,
                       v26,
                       v36,
                       v27,
                       v20,
                       v19,
                       v18,
                       0,
                       0,
                       v25);
        }
        WindowsDeleteString(v22);
        goto LABEL_19;
      }
      if ( v10 == 3 )
      {
        v22 = 0;
        Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v22);
        Instance = Windows::ApplicationModel::Contacts::Internal::DeserializeMapActivationContext(a3, &v22, v16);
        if ( Instance >= 0 )
        {
          v29[0] = (__int64)v22;
          v32 = 0;
          Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v31, &pszDefault, 1u, 0);
          v29[2] = v32;
          v29[3] = (__int64)v26;
          string = 0;
          v28 = 0;
          v29[1] = (__int64)v4;
          Instance = Microsoft::WRL::Details::MakeAndInitialize<Windows::ApplicationModel::Contacts::Internal::MapActionControlItem,Windows::ApplicationModel::Contacts::Internal::IContactActionControlItem,Windows::ApplicationModel::Contacts::IContact2 * &,HSTRING__ * &,HSTRING__ * &,Windows::ApplicationModel::Contacts::IContactAddress * &,IShellItem * &,Windows::ApplicationModel::Contacts::Internal::IContactPreferenceManager * &>(
                       v25,
                       (__int64)v29,
                       (__int64)&v28,
                       (__int64)&string);
        }
        Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v22);
        goto LABEL_19;
      }
      if ( v10 - 4 <= 1 )
      {
LABEL_8:
        WindowsDeleteString(0);
        string = 0;
        WindowsDeleteString(0);
        v22 = 0;
        v12 = Windows::ApplicationModel::Contacts::Internal::DeserializeServiceActivationContext(
                a3,
                (HSTRING)&v22,
                &string,
                v11);
        v13 = v22;
        Instance = v12;
        v14 = string;
        if ( v12 >= 0 )
        {
          v36 = 0;
          Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, &pszDefault, 1u, 0);
          v15 = v36;
          v34 = 0;
          Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v33, &pszDefault, 1u, 0);
          Instance = Windows::ApplicationModel::Contacts::Internal::ContactActionControlItem_CreateInstance(
                       v10,
                       v26,
                       v34,
                       v27,
                       v15,
                       v13,
                       v14,
                       0,
                       0,
                       v25);
        }
        WindowsDeleteString(v14);
        WindowsDeleteString(v13);
      }
    }
    else
    {
      v7 = 0;
    }
LABEL_19:
    v4 = v27;
    StringRawBuffer = v30;
    if ( (unsigned __int64)++v9 >= 6 )
      return (unsigned int)Instance;
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1801cd044  push    rbp
0x1801cd046  push    rbx
0x1801cd047  push    rsi
0x1801cd048  push    rdi
0x1801cd049  push    r12
0x1801cd04b  push    r13
0x1801cd04d  push    r14
0x1801cd04f  push    r15
0x1801cd051  lea     rbp, [rsp-28h]
0x1801cd056  sub     rsp, 128h
0x1801cd05d  mov     rax, cs:__security_cookie
0x1801cd064  xor     rax, rsp
0x1801cd067  mov     [rbp+60h+var_50], rax
0x1801cd06b  mov     rdi, rdx
0x1801cd06e  mov     [rsp+160h+var_E8], rdx
0x1801cd073  mov     [rsp+160h+var_F0], rcx
0x1801cd078  lea     rdx, [rsp+160h+length]; length
0x1801cd07d  xor     r15d, r15d
0x1801cd080  mov     [rsp+160h+var_F8], r9
0x1801cd085  mov     rcx, rdi; string
0x1801cd088  mov     [rsp+160h+length], r15d
0x1801cd08d  mov     r13, r8
0x1801cd090  call    cs:__imp_WindowsGetStringRawBuffer
0x1801cd096  mov     [rbp+60h+var_B8], rax
0x1801cd09a  mov     r12b, r15b
0x1801cd09d  mov     esi, 80070057h
0x1801cd0a2  lea     rcx, off_1803E1770; "Windows.Contact.Call"
0x1801cd0a9  mov     r14d, r15d
0x1801cd0ac  test    r12b, r12b
0x1801cd0af  jnz     loc_1801CD3A1
0x1801cd0b5  mov     edx, [rsp+160h+length]; cchCount1
0x1801cd0b9  mov     rbx, r14
0x1801cd0bc  add     rbx, rbx
0x1801cd0bf  mov     [rsp+160h+bIgnoreCase], 1; bIgnoreCase
0x1801cd0c7  or      r9d, 0FFFFFFFFh; cchCount2
0x1801cd0cb  mov     r8, [rcx+rbx*8]; lpString2
0x1801cd0cf  mov     rcx, rax; lpString1
0x1801cd0d2  call    cs:__imp_CompareStringOrdinal
0x1801cd0d8  cmp     eax, 2
0x1801cd0db  jnz     loc_1801CD381
0x1801cd0e1  lea     r15, off_1803E1770; "Windows.Contact.Call"
0x1801cd0e8  mov     r12b, 1
0x1801cd0eb  mov     r15d, [r15+rbx*8+8]
0x1801cd0f0  mov     ecx, r15d
0x1801cd0f3  test    r15d, r15d
0x1801cd0f6  jz      short loc_1801CD11D
0x1801cd0f8  sub     ecx, 1
0x1801cd0fb  jz      short loc_1801CD11D
0x1801cd0fd  sub     ecx, 1
0x1801cd100  jz      loc_1801CD2AE
0x1801cd106  sub     ecx, 1
0x1801cd109  jz      loc_1801CD204
0x1801cd10f  sub     ecx, 1
0x1801cd112  jz      short loc_1801CD11D
0x1801cd114  cmp     ecx, 1
0x1801cd117  jnz     loc_1801CD1FC
0x1801cd11d  xor     ecx, ecx; string
0x1801cd11f  call    cs:__imp_WindowsDeleteString
0x1801cd125  xor     ecx, ecx; string
0x1801cd127  mov     [rsp+160h+string], 0
0x1801cd130  call    cs:__imp_WindowsDeleteString
0x1801cd136  lea     r8, [rsp+160h+string]; HSTRING *
0x1801cd13b  mov     [rsp+160h+var_110], 0
0x1801cd144  lea     rdx, [rsp+160h+var_110]; HSTRING
0x1801cd149  mov     rcx, r13; this
0x1801cd14c  call    ?DeserializeServiceActivationContext@Internal@Contacts@ApplicationModel@Windows@@YAJPEAUHSTRING__@@PEAPEAU5@1@Z; Windows::ApplicationModel::Contacts::Internal::DeserializeServiceActivationContext(HSTRING__ *,HSTRING__ * *,HSTRING__ * *)
0x1801cd151  mov     rbx, [rsp+160h+var_110]
0x1801cd156  mov     esi, eax
0x1801cd158  mov     rdi, [rsp+160h+string]
0x1801cd15d  test    eax, eax
0x1801cd15f  js      loc_1801CD1EA
0x1801cd165  xor     r9d, r9d; unsigned int
0x1801cd168  mov     [rbp+60h+var_58], 0
0x1801cd170  lea     rdx, pszDefault; sourceString
0x1801cd177  lea     rcx, [rbp+60h+hstringHeader]; hstringHeader
0x1801cd17b  lea     r8d, [r9+1]; unsigned int
0x1801cd17f  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1801cd184  mov     rsi, [rbp+60h+var_58]
0x1801cd188  lea     rdx, pszDefault; sourceString
0x1801cd18f  xor     r9d, r9d; unsigned int
0x1801cd192  mov     [rbp+60h+var_78], 0
0x1801cd19a  lea     rcx, [rbp+60h+var_90]; hstringHeader
0x1801cd19e  lea     r8d, [r9+1]; unsigned int
0x1801cd1a2  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1801cd1a7  mov     rax, [rsp+160h+var_F8]
0x1801cd1ac  mov     ecx, r15d
0x1801cd1af  mov     r9, [rsp+160h+var_E8]
0x1801cd1b4  mov     r8, [rbp+60h+var_78]
0x1801cd1b8  mov     rdx, [rsp+160h+var_F0]
0x1801cd1bd  mov     [rsp+160h+var_118], rax
0x1801cd1c2  mov     [rsp+160h+var_120], 0
0x1801cd1cb  mov     [rsp+160h+var_128], 0
0x1801cd1d4  mov     [rsp+160h+var_130], rdi
0x1801cd1d9  mov     [rsp+160h+var_138], rbx
0x1801cd1de  mov     qword ptr [rsp+160h+bIgnoreCase], rsi
0x1801cd1e3  call    ?ContactActionControlItem_CreateInstance@Internal@Contacts@ApplicationModel@Windows@@YAJW4ControlType@1234@PEAUIContact2@234@PEAUHSTRING__@@2222PEAUIShellItem@@PEAUIContactPreferenceManager@1234@PEAPEAUIContactActionControlItem@1234@@Z; Windows::ApplicationModel::Contacts::Internal::ContactActionControlItem_CreateInstance(Windows::ApplicationModel::Contacts::Internal::ControlType,Windows::ApplicationModel::Contacts::IContact2 *,HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ *,IShellItem *,Windows::ApplicationModel::Contacts::Internal::IContactPreferenceManager *,Windows::ApplicationModel::Contacts::Internal::IContactActionControlItem * *)
0x1801cd1e8  mov     esi, eax
0x1801cd1ea  mov     rcx, rdi; string
0x1801cd1ed  call    cs:__imp_WindowsDeleteString
0x1801cd1f3  mov     rcx, rbx; string
0x1801cd1f6  call    cs:__imp_WindowsDeleteString
0x1801cd1fc  xor     r15d, r15d
0x1801cd1ff  jmp     loc_1801CD384
0x1801cd204  xor     r15d, r15d
0x1801cd207  lea     rcx, [rsp+160h+var_110]
0x1801cd20c  mov     [rsp+160h+var_110], r15
0x1801cd211  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1801cd216  lea     rdx, [rsp+160h+var_110]; HSTRING
0x1801cd21b  mov     rcx, r13; this
0x1801cd21e  call    ?DeserializeMapActivationContext@Internal@Contacts@ApplicationModel@Windows@@YAJPEAUHSTRING__@@PEAPEAUIContactAddress@234@@Z; Windows::ApplicationModel::Contacts::Internal::DeserializeMapActivationContext(HSTRING__ *,Windows::ApplicationModel::Contacts::IContactAddress * *)
0x1801cd223  mov     esi, eax
0x1801cd225  test    eax, eax
0x1801cd227  js      short loc_1801CD29F
0x1801cd229  mov     rax, [rsp+160h+var_110]
0x1801cd22e  lea     r8d, [r15+1]; unsigned int
0x1801cd232  xor     r9d, r9d; unsigned int
0x1801cd235  mov     [rbp+60h+var_D8], rax
0x1801cd239  lea     rdx, pszDefault; sourceString
0x1801cd240  mov     [rbp+60h+var_98], r15
0x1801cd244  lea     rcx, [rbp+60h+var_B0]; hstringHeader
0x1801cd248  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1801cd24d  mov     rax, [rbp+60h+var_98]
0x1801cd251  lea     r9, [rbp+60h+var_D0]
0x1801cd255  mov     rcx, [rsp+160h+var_F8]; void **
0x1801cd25a  lea     r8, [rbp+60h+var_C8]
0x1801cd25e  mov     [rbp+60h+var_C8], rax
0x1801cd262  lea     rdx, [rbp+60h+var_C0]
0x1801cd266  mov     rax, [rsp+160h+var_F0]
0x1801cd26b  mov     [rbp+60h+var_C0], rax
0x1801cd26f  lea     rax, [rsp+160h+string]
0x1801cd274  mov     [rsp+160h+var_130], rax; __int64
0x1801cd279  lea     rax, [rbp+60h+var_E0]
0x1801cd27d  mov     [rsp+160h+var_138], rax; __int64
0x1801cd282  lea     rax, [rbp+60h+var_D8]
0x1801cd286  mov     qword ptr [rsp+160h+bIgnoreCase], rax; __int64
0x1801cd28b  mov     [rsp+160h+string], r15
0x1801cd290  mov     [rbp+60h+var_E0], r15
0x1801cd294  mov     [rbp+60h+var_D0], rdi
0x1801cd298  call    ??$MakeAndInitialize@VMapActionControlItem@Internal@Contacts@ApplicationModel@Windows@@UIContactActionControlItem@2345@AEAPEAUIContact2@345@AEAPEAUHSTRING__@@AEAPEAU8@AEAPEAUIContactAddress@345@AEAPEAUIShellItem@@AEAPEAUIContactPreferenceManager@2345@@Details@WRL@Microsoft@@YAJPEAPEAUIContactActionControlItem@Internal@Contacts@ApplicationModel@Windows@@AEAPEAUIContact2@567@AEAPEAUHSTRING__@@2AEAPEAUIContactAddress@567@AEAPEAUIShellItem@@AEAPEAUIContactPreferenceManager@4567@@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::ApplicationModel::Contacts::Internal::MapActionControlItem,Windows::ApplicationModel::Contacts::Internal::IContactActionControlItem,Windows::ApplicationModel::Contacts::IContact2 * &,HSTRING__ * &,HSTRING__ * &,Windows::ApplicationModel::Contacts::IContactAddress * &,IShellItem * &,Windows::ApplicationModel::Contacts::Internal::IContactPreferenceManager * &>(Windows::ApplicationModel::Contacts::Internal::IContactActionControlItem * *,Windows::ApplicationModel::Contacts::IContact2 * &,HSTRING__ * &,HSTRING__ * &,Windows::ApplicationModel::Contacts::IContactAddress * &,IShellItem * &,Windows::ApplicationModel::Contacts::Internal::IContactPreferenceManager * &)
0x1801cd29d  mov     esi, eax
0x1801cd29f  lea     rcx, [rsp+160h+var_110]
0x1801cd2a4  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1801cd2a9  jmp     loc_1801CD384
0x1801cd2ae  xor     r15d, r15d
0x1801cd2b1  xor     ecx, ecx; string
0x1801cd2b3  mov     [rsp+160h+var_110], r15
0x1801cd2b8  call    cs:__imp_WindowsDeleteString
0x1801cd2be  lea     rdx, [rsp+160h+var_110]; HSTRING
0x1801cd2c3  mov     [rsp+160h+var_110], r15
0x1801cd2c8  mov     rcx, r13; this
0x1801cd2cb  call    ?DeserializeEmailActivationContext@Internal@Contacts@ApplicationModel@Windows@@YAJPEAUHSTRING__@@PEAPEAU5@@Z; Windows::ApplicationModel::Contacts::Internal::DeserializeEmailActivationContext(HSTRING__ *,HSTRING__ * *)
0x1801cd2d0  mov     esi, eax
0x1801cd2d2  test    eax, eax
0x1801cd2d4  js      loc_1801CD374
0x1801cd2da  xor     r9d, r9d; unsigned int
0x1801cd2dd  mov     [rbp+60h+var_98], r15
0x1801cd2e1  lea     r8d, [r15+1]; unsigned int
0x1801cd2e5  lea     rdx, pszDefault; sourceString
0x1801cd2ec  lea     rcx, [rbp+60h+var_B0]; hstringHeader
0x1801cd2f0  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1801cd2f5  mov     rdi, [rbp+60h+var_98]
0x1801cd2f9  lea     r8d, [r15+1]; unsigned int
0x1801cd2fd  mov     rsi, [rsp+160h+var_110]
0x1801cd302  lea     rdx, pszDefault; sourceString
0x1801cd309  xor     r9d, r9d; unsigned int
0x1801cd30c  mov     [rbp+60h+var_78], r15
0x1801cd310  lea     rcx, [rbp+60h+var_90]; hstringHeader
0x1801cd314  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1801cd319  mov     rbx, [rbp+60h+var_78]
0x1801cd31d  lea     r8d, [r15+1]; unsigned int
0x1801cd321  xor     r9d, r9d; unsigned int
0x1801cd324  mov     [rbp+60h+var_58], r15
0x1801cd328  lea     rdx, pszDefault; sourceString
0x1801cd32f  lea     rcx, [rbp+60h+hstringHeader]; hstringHeader
0x1801cd333  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1801cd338  mov     rax, [rsp+160h+var_F8]
0x1801cd33d  lea     ecx, [r15+2]
0x1801cd341  mov     r9, [rsp+160h+var_E8]
0x1801cd346  mov     r8, [rbp+60h+var_58]
0x1801cd34a  mov     rdx, [rsp+160h+var_F0]
0x1801cd34f  mov     [rsp+160h+var_118], rax
0x1801cd354  mov     [rsp+160h+var_120], r15
0x1801cd359  mov     [rsp+160h+var_128], r15
0x1801cd35e  mov     [rsp+160h+var_130], rdi
0x1801cd363  mov     [rsp+160h+var_138], rsi
0x1801cd368  mov     qword ptr [rsp+160h+bIgnoreCase], rbx
0x1801cd36d  call    ?ContactActionControlItem_CreateInstance@Internal@Contacts@ApplicationModel@Windows@@YAJW4ControlType@1234@PEAUIContact2@234@PEAUHSTRING__@@2222PEAUIShellItem@@PEAUIContactPreferenceManager@1234@PEAPEAUIContactActionControlItem@1234@@Z; Windows::ApplicationModel::Contacts::Internal::ContactActionControlItem_CreateInstance(Windows::ApplicationModel::Contacts::Internal::ControlType,Windows::ApplicationModel::Contacts::IContact2 *,HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ *,IShellItem *,Windows::ApplicationModel::Contacts::Internal::IContactPreferenceManager *,Windows::ApplicationModel::Contacts::Internal::IContactActionControlItem * *)
0x1801cd372  mov     esi, eax
0x1801cd374  mov     rcx, [rsp+160h+var_110]; string
0x1801cd379  call    cs:__imp_WindowsDeleteString
0x1801cd37f  jmp     short loc_1801CD384
0x1801cd381  mov     r12b, r15b
0x1801cd384  mov     rdi, [rsp+160h+var_E8]
0x1801cd389  lea     rcx, off_1803E1770; "Windows.Contact.Call"
0x1801cd390  mov     rax, [rbp+60h+var_B8]
0x1801cd394  inc     r14
0x1801cd397  cmp     r14, 6
0x1801cd39b  jb      loc_1801CD0AC
0x1801cd3a1  mov     eax, esi
0x1801cd3a3  mov     rcx, [rbp+60h+var_50]
0x1801cd3a7  xor     rcx, rsp; StackCookie
0x1801cd3aa  call    __security_check_cookie
0x1801cd3af  add     rsp, 128h
0x1801cd3b6  pop     r15
0x1801cd3b8  pop     r14
0x1801cd3ba  pop     r13
0x1801cd3bc  pop     r12
0x1801cd3be  pop     rdi
0x1801cd3bf  pop     rsi
0x1801cd3c0  pop     rbx
0x1801cd3c1  pop     rbp
0x1801cd3c2  retn
```
