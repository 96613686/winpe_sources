# CDataProviderRequest::RuntimeClassInitialize(Windows::ApplicationModel::DataTransfer::IDataPackage *,ushort const *,ulong)

- ea: `0x180049a94`
- end: `0x180049c81`
- name: `?RuntimeClassInitialize@CDataProviderRequest@@QEAAJPEAUIDataPackage@DataTransfer@ApplicationModel@Windows@@PEBGK@Z`
- size: `493`
- prototype: `int(CDataProviderRequest *__hidden this, struct Windows::ApplicationModel::DataTransfer::IDataPackage *, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18005dcac`

## callees

- `0x180037c14`
- `0x180049a94`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180049bcd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180049bcd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180049bb5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180049bb5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180049c11`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180049c11`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180049b18`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180049b18`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CDataProviderRequest::RuntimeClassInitialize(
        CDataProviderRequest *this,
        struct IUnknown *a2,
        const unsigned __int16 *a3,
        unsigned int a4)
{
  unsigned __int64 v4; // r13
  HRESULT Instance; // ebx
  HSTRING v9; // rsi
  __int64 (__fastcall *v10)(HSTRING, char *); // r15
  __int64 v11; // rcx
  HSTRING v12; // rcx
  unsigned __int64 v13; // rdx
  HSTRING v14; // rcx
  __int64 v15; // rbx
  unsigned __int64 v16; // rax
  __int64 v17; // rcx
  _QWORD v19[3]; // [rsp+30h] [rbp-18h] BYREF
  HSTRING string; // [rsp+98h] [rbp+50h] BYREF

  v4 = a4;
  v19[0] = 0;
  Instance = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, _QWORD *))a2->lpVtbl->QueryInterface)(
               a2,
               &GUID_cd1c0ba1_0ccb_4a33_9652_fe27a738c219,
               v19);
  if ( Instance >= 0 )
  {
    Instance = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v19[0] + 56LL))(v19[0]);
    if ( !Instance )
    {
      string = 0;
      Instance = CoCreateInstance(
                   &GUID_228826af_02e1_4226_a9e0_99a855e455a6,
                   0,
                   4u,
                   &GUID_9767060c_9476_42e2_8f7b_2f10fd13765c,
                   (LPVOID *)&string);
      if ( Instance >= 0 )
      {
        v9 = string;
        v10 = *(__int64 (__fastcall **)(HSTRING, char *))(*(_QWORD *)string + 88LL);
        v11 = *((_QWORD *)this + 15);
        if ( v11 )
        {
          *((_QWORD *)this + 15) = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
        }
        Instance = v10(v9, (char *)this + 120);
      }
      v12 = string;
      if ( string )
      {
        string = 0;
        (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v12 + 16LL))(v12);
      }
    }
    if ( Instance >= 0 )
    {
      if ( a3 )
      {
        string = 0;
        v13 = -1;
        do
          ++v13;
        while ( a3[v13] );
        if ( v13 > 0xFFFFFFFF )
        {
          Instance = -2147024362;
        }
        else
        {
          Instance = WindowsCreateString(a3, v13, &string);
          if ( Instance >= 0 )
          {
            v14 = (HSTRING)*((_QWORD *)this + 9);
            *((_QWORD *)this + 9) = string;
            WindowsDeleteString(v14);
          }
        }
        if ( Instance >= 0 )
        {
          Instance = AgileGitPtr::Initialize(
                       (CDataProviderRequest *)((char *)this + 88),
                       &GUID_61ebf5c7_efea_4346_9554_981d7e198ffe,
                       a2);
          if ( Instance >= 0 )
          {
            string = 0;
            v15 = 10000 * v4;
            if ( is_mul_ok(v4, 0x2710u)
              && (string = 0,
                  GetSystemTimeAsFileTime((LPFILETIME)&string),
                  v16 = (unsigned __int64)string + v15,
                  (HSTRING)((char *)string + v15) >= string) )
            {
              if ( (v16 & 0x8000000000000000uLL) == 0LL )
              {
                *((_QWORD *)this + 10) = (unsigned int)v16 | (HIDWORD(v16) << 32);
                Instance = 0;
              }
              else
              {
                Instance = -2147483637;
              }
            }
            else
            {
              Instance = -2147024362;
            }
          }
        }
      }
      else
      {
        Instance = -2147467261;
      }
    }
  }
  v17 = v19[0];
  if ( v19[0] )
  {
    v19[0] = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180049a94  push    rbp
0x180049a96  push    rbx
0x180049a97  push    rsi
0x180049a98  push    rdi
0x180049a99  push    r12
0x180049a9b  push    r13
0x180049a9d  push    r14
0x180049a9f  push    r15
0x180049aa1  mov     rbp, rsp
0x180049aa4  sub     rsp, 48h
0x180049aa8  mov     r13d, r9d
0x180049aab  mov     r14, r8
0x180049aae  mov     r12, rdx
0x180049ab1  mov     rdi, rcx
0x180049ab4  xor     esi, esi
0x180049ab6  mov     [rbp+var_18], rsi
0x180049aba  mov     rax, [rdx]
0x180049abd  lea     r8, [rbp+var_18]
0x180049ac1  lea     rdx, _GUID_cd1c0ba1_0ccb_4a33_9652_fe27a738c219
0x180049ac8  mov     rcx, r12
0x180049acb  mov     rax, [rax]
0x180049ace  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049ad3  mov     ebx, eax
0x180049ad5  test    eax, eax
0x180049ad7  js      loc_180049C54
0x180049add  mov     rcx, [rbp+var_18]
0x180049ae1  mov     rax, [rcx]
0x180049ae4  mov     rax, [rax+38h]
0x180049ae8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049aed  mov     ebx, eax
0x180049aef  test    eax, eax
0x180049af1  jnz     loc_180049B7B
0x180049af7  mov     [rbp+string], rsi
0x180049afb  lea     rax, [rbp+string]
0x180049aff  mov     [rsp+48h+ppv], rax; ppv
0x180049b04  lea     r9, _GUID_9767060c_9476_42e2_8f7b_2f10fd13765c; riid
0x180049b0b  xor     edx, edx; pUnkOuter
0x180049b0d  lea     r8d, [rsi+4]; dwClsContext
0x180049b11  lea     rcx, _GUID_228826af_02e1_4226_a9e0_99a855e455a6; rclsid
0x180049b18  call    cs:__imp_CoCreateInstance
0x180049b1e  mov     ebx, eax
0x180049b20  test    eax, eax
0x180049b22  js      short loc_180049B61
0x180049b24  mov     rsi, [rbp+string]
0x180049b28  mov     rax, [rsi]
0x180049b2b  mov     r15, [rax+58h]
0x180049b2f  lea     rbx, [rdi+78h]
0x180049b33  mov     rcx, [rbx]
0x180049b36  test    rcx, rcx
0x180049b39  jz      short loc_180049B4F
0x180049b3b  mov     qword ptr [rbx], 0
0x180049b42  mov     r8, [rcx]
0x180049b45  mov     rax, [r8+10h]
0x180049b49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049b4e  nop
0x180049b4f  mov     rdx, rbx
0x180049b52  mov     rcx, rsi
0x180049b55  mov     rax, r15
0x180049b58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049b5d  mov     ebx, eax
0x180049b5f  xor     esi, esi
0x180049b61  mov     rcx, [rbp+string]
0x180049b65  test    rcx, rcx
0x180049b68  jz      short loc_180049B7B
0x180049b6a  mov     [rbp+string], rsi
0x180049b6e  mov     rax, [rcx]
0x180049b71  mov     rax, [rax+10h]
0x180049b75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049b7a  nop
0x180049b7b  test    ebx, ebx
0x180049b7d  js      loc_180049C54
0x180049b83  test    r14, r14
0x180049b86  jz      loc_180049C4F
0x180049b8c  mov     [rbp+string], rsi
0x180049b90  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180049b94  inc     rdx; length
0x180049b97  cmp     [r14+rdx*2], si
0x180049b9c  jnz     short loc_180049B94
0x180049b9e  mov     eax, 0FFFFFFFFh
0x180049ba3  mov     r15d, 80070216h
0x180049ba9  cmp     rdx, rax
0x180049bac  ja      short loc_180049BD5
0x180049bae  lea     r8, [rbp+string]; string
0x180049bb2  mov     rcx, r14; sourceString
0x180049bb5  call    cs:__imp_WindowsCreateString
0x180049bbb  mov     ebx, eax
0x180049bbd  test    eax, eax
0x180049bbf  js      short loc_180049BD8
0x180049bc1  mov     rcx, [rdi+48h]; string
0x180049bc5  mov     rax, [rbp+string]
0x180049bc9  mov     [rdi+48h], rax
0x180049bcd  call    cs:__imp_WindowsDeleteString
0x180049bd3  jmp     short loc_180049BD8
0x180049bd5  mov     ebx, r15d
0x180049bd8  test    ebx, ebx
0x180049bda  js      short loc_180049C54
0x180049bdc  lea     rcx, [rdi+58h]; this
0x180049be0  mov     r8, r12; struct IUnknown *
0x180049be3  lea     rdx, _GUID_61ebf5c7_efea_4346_9554_981d7e198ffe; struct _GUID *
0x180049bea  call    ?Initialize@AgileGitPtr@@QEAAJAEBU_GUID@@PEAUIUnknown@@@Z; AgileGitPtr::Initialize(_GUID const &,IUnknown *)
0x180049bef  mov     ebx, eax
0x180049bf1  test    eax, eax
0x180049bf3  js      short loc_180049C54
0x180049bf5  mov     [rbp+string], rsi
0x180049bf9  mov     eax, 2710h
0x180049bfe  mul     r13
0x180049c01  mov     rbx, rax
0x180049c04  test    rdx, rdx
0x180049c07  jnz     short loc_180049C4A
0x180049c09  mov     [rbp+string], rsi
0x180049c0d  lea     rcx, [rbp+string]; lpSystemTimeAsFileTime
0x180049c11  call    cs:__imp_GetSystemTimeAsFileTime
0x180049c17  mov     rcx, [rbp+string]
0x180049c1b  lea     rax, [rcx+rbx]
0x180049c1f  cmp     rax, rcx
0x180049c22  jb      short loc_180049C4A
0x180049c24  mov     rcx, rax
0x180049c27  shr     rcx, 20h
0x180049c2b  test    ecx, ecx
0x180049c2d  jns     short loc_180049C36
0x180049c2f  mov     ebx, 8000000Bh
0x180049c34  jmp     short loc_180049C54
0x180049c36  mov     rdx, rcx
0x180049c39  shl     rdx, 20h
0x180049c3d  mov     ecx, eax
0x180049c3f  or      rdx, rcx
0x180049c42  mov     [rdi+50h], rdx
0x180049c46  mov     ebx, esi
0x180049c48  jmp     short loc_180049C54
0x180049c4a  mov     ebx, r15d
0x180049c4d  jmp     short loc_180049C54
0x180049c4f  mov     ebx, 80004003h
0x180049c54  mov     rcx, [rbp+var_18]
0x180049c58  test    rcx, rcx
0x180049c5b  jz      short loc_180049C6E
0x180049c5d  mov     [rbp+var_18], rsi
0x180049c61  mov     rax, [rcx]
0x180049c64  mov     rax, [rax+10h]
0x180049c68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049c6d  nop
0x180049c6e  mov     eax, ebx
0x180049c70  add     rsp, 48h
0x180049c74  pop     r15
0x180049c76  pop     r14
0x180049c78  pop     r13
0x180049c7a  pop     r12
0x180049c7c  pop     rdi
0x180049c7d  pop     rsi
0x180049c7e  pop     rbx
0x180049c7f  pop     rbp
0x180049c80  retn
```
