# ResolveUri_File(unsigned __int64,ushort const *,ushort const *,ushort const *,DEVICE_SCALE_FACTOR *,RESOURCE_CONTRAST *,ushort * *)

- ea: `0x18000f750`
- end: `0x18000fb3a`
- name: `?ResolveUri_File@@YAJ_KPEBG11PEAW4DEVICE_SCALE_FACTOR@@PEAW4RESOURCE_CONTRAST@@PEAPEAG@Z`
- size: `1002`
- prototype: `int(unsigned __int64, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, enum DEVICE_SCALE_FACTOR *, enum RESOURCE_CONTRAST *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x180005670`
- `0x18000f750`
- `0x18001ff00`
- `0x180020d34`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f967`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f967`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000f848`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000f9d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000f848`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000f9d9`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f904`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f904`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000f946`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000f946`
- `urlmon!CreateUri` at `0x18000f7c5`
- `urlmon!CreateUri` at `0x18000f7c5`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall ResolveUri_File(
        __int64 a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        enum DEVICE_SCALE_FACTOR *a5,
        enum RESOURCE_CONTRAST *a6,
        unsigned __int16 **a7)
{
  unsigned __int64 v8; // rbx
  _WORD *v9; // r15
  HRESULT v10; // ebp
  int v11; // r13d
  BSTR v12; // rsi
  unsigned __int64 v13; // rdi
  unsigned __int64 v14; // r14
  OLECHAR *v15; // r10
  unsigned __int64 v16; // rdx
  OLECHAR *v17; // r8
  __int64 v18; // rcx
  OLECHAR v19; // ax
  __int64 v20; // r9
  OLECHAR *v21; // rcx
  __int64 v22; // r14
  bool v23; // cf
  IUri *v24; // rcx
  const WCHAR *v25; // rcx
  unsigned __int16 *v27; // rax
  unsigned __int16 *v28; // r11
  WCHAR *v29; // rcx
  unsigned __int64 v30; // rdx
  unsigned __int16 *v31; // r8
  __int64 v32; // r9
  WCHAR v33; // ax
  __int64 v34; // r10
  unsigned __int16 *v35; // rcx
  __int64 v36; // rdi
  unsigned __int64 v37; // rdi
  IUri *ppURI; // [rsp+20h] [rbp-2A8h] BYREF
  BSTR bstrString[2]; // [rsp+28h] [rbp-2A0h] BYREF
  _WORD *v40; // [rsp+38h] [rbp-290h]
  __int64 v41; // [rsp+40h] [rbp-288h]
  __int64 v42; // [rsp+48h] [rbp-280h]
  __int64 v43; // [rsp+50h] [rbp-278h]
  WCHAR Dst[264]; // [rsp+60h] [rbp-268h] BYREF

  *a7 = 0;
  v43 = 0;
  v8 = -1;
  v41 = -1;
  v42 = -1;
  v9 = 0;
  v40 = 0;
  ppURI = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppURI);
  v10 = CreateUri(a2, 0x8020u, 0, &ppURI);
  v11 = -2147024882;
  if ( v10 >= 0 )
  {
    bstrString[0] = 0;
    v10 = ((__int64 (__fastcall *)(IUri *, BSTR *))ppURI->lpVtbl->GetPath)(ppURI, bstrString);
    if ( v10 >= 0 )
    {
      v12 = bstrString[0];
      v13 = -1;
      do
        ++v13;
      while ( bstrString[0][v13] );
      v9 = 0;
      v40 = 0;
      v14 = v13 + 1;
      if ( v13 + 1 < v13 )
      {
        v10 = -2147024362;
      }
      else
      {
        v40 = 0;
        if ( is_mul_ok(v14, 2u) )
        {
          v9 = CoTaskMemAlloc(2 * v14);
          v40 = v9;
          v10 = -2147024882;
          if ( v9 )
            v10 = 0;
          v15 = v9;
        }
        else
        {
          v15 = 0;
          v10 = -2147024362;
        }
        if ( v10 >= 0 )
        {
          if ( (v15 || v13 == -1) && v14 <= 0x7FFFFFFF )
          {
            if ( v13 >= 0x7FFFFFFF )
            {
              if ( v13 != -1 )
                *v15 = 0;
            }
            else
            {
              if ( !v12 )
              {
                v12 = (BSTR)&pwzBaseUrl;
                v13 = 0;
              }
              if ( v14 )
              {
                v16 = v14;
                v17 = v15;
                v18 = 0;
                do
                {
                  if ( !v13 )
                    break;
                  v19 = *v12;
                  if ( !*v12 )
                    break;
                  ++v12;
                  *v17++ = v19;
                  --v13;
                  ++v18;
                  --v16;
                }
                while ( v16 );
                v20 = v18 - 1;
                if ( v16 )
                  v20 = v18;
                v21 = v17 - 1;
                if ( v16 )
                  v21 = v17;
                *v21 = 0;
                if ( v16 )
                {
                  v23 = v14 == v20;
                  v22 = v14 - v20;
                  if ( !v23 && v22 != 1 && (unsigned __int64)(2 * v22) > 2 )
                    memset_0(&v15[v20 + 1], 0, 2 * v22 - 2);
                }
              }
            }
          }
          else
          {
            *v15 = 0;
          }
        }
      }
      SysFreeString(bstrString[0]);
    }
  }
  v24 = ppURI;
  if ( ppURI )
  {
    ppURI = 0;
    ((void (__fastcall *)(IUri *))v24->lpVtbl->Release)(v24);
  }
  if ( v10 < 0 )
  {
    v11 = v10;
  }
  else
  {
    v25 = v9;
    if ( *v9 == 92 )
      v25 = v9 + 1;
    if ( ExpandEnvironmentStringsW(v25, Dst, 0x104u) - 1 <= 0x103 )
    {
      do
        ++v8;
      while ( Dst[v8] );
      *a7 = 0;
      v37 = v8 + 1;
      if ( v8 + 1 >= v8 && is_mul_ok(v37, 2u) )
      {
        v27 = (unsigned __int16 *)CoTaskMemAlloc(2 * v37);
        v28 = v27;
        *a7 = v27;
        if ( v27 )
          v11 = 0;
        if ( v11 >= 0 )
        {
          if ( (v27 || v8 == -1) && v37 <= 0x7FFFFFFF )
          {
            if ( v8 >= 0x7FFFFFFF )
            {
              if ( v8 != -1 )
                *v27 = 0;
            }
            else
            {
              v29 = Dst;
              v30 = v8 + 1;
              v31 = v27;
              v32 = 0;
              do
              {
                if ( !v8 )
                  break;
                v33 = *v29;
                if ( !*v29 )
                  break;
                ++v29;
                *v31++ = v33;
                --v8;
                ++v32;
                --v30;
              }
              while ( v30 );
              v34 = v32 - 1;
              if ( v30 )
                v34 = v32;
              v35 = v31 - 1;
              if ( v30 )
                v35 = v31;
              *v35 = 0;
              if ( v30 )
              {
                v23 = v37 == v34;
                v36 = v37 - v34;
                if ( !v23 && v36 != 1 && (unsigned __int64)(2 * v36) > 2 )
                  memset_0(&v28[v34 + 1], 0, 2 * v36 - 2);
              }
            }
          }
          else
          {
            *v27 = 0;
          }
        }
      }
      else
      {
        v11 = -2147024362;
      }
    }
    else
    {
      v11 = -2147024774;
    }
  }
  if ( v9 )
    CoTaskMemFree(v9);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18000f750  push    rbx
0x18000f752  push    rbp
0x18000f753  push    rsi
0x18000f754  push    rdi
0x18000f755  push    r12
0x18000f757  push    r13
0x18000f759  push    r14
0x18000f75b  push    r15
0x18000f75d  sub     rsp, 288h
0x18000f764  mov     rax, cs:__security_cookie
0x18000f76b  xor     rax, rsp
0x18000f76e  mov     [rsp+2C8h+var_58], rax
0x18000f776  mov     rdi, rdx
0x18000f779  mov     r12, [rsp+2C8h+arg_30]
0x18000f781  xor     r14d, r14d
0x18000f784  mov     [r12], r14
0x18000f788  mov     [rsp+2C8h+var_278], r14
0x18000f78d  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18000f794  mov     [rsp+2C8h+var_288], rbx
0x18000f799  mov     [rsp+2C8h+var_280], rbx
0x18000f79e  mov     r15d, r14d
0x18000f7a1  mov     [rsp+2C8h+var_290], r14
0x18000f7a6  mov     [rsp+2C8h+ppURI], r14
0x18000f7ab  lea     rcx, [rsp+2C8h+ppURI]
0x18000f7b0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000f7b5  lea     r9, [rsp+2C8h+ppURI]; ppURI
0x18000f7ba  xor     r8d, r8d; dwReserved
0x18000f7bd  mov     edx, 8020h; dwFlags
0x18000f7c2  mov     rcx, rdi; pwzURI
0x18000f7c5  call    cs:__imp_CreateUri
0x18000f7cb  mov     ebp, eax
0x18000f7cd  mov     r13d, 8007000Eh
0x18000f7d3  test    eax, eax
0x18000f7d5  js      loc_18000F90D
0x18000f7db  mov     [rsp+2C8h+bstrString], r14
0x18000f7e0  mov     rcx, [rsp+2C8h+ppURI]
0x18000f7e5  mov     rax, [rcx]
0x18000f7e8  lea     rdx, [rsp+2C8h+bstrString]
0x18000f7ed  mov     rax, [rax+78h]
0x18000f7f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f7f6  mov     ebp, eax
0x18000f7f8  test    eax, eax
0x18000f7fa  js      loc_18000F90D
0x18000f800  mov     rsi, [rsp+2C8h+bstrString]
0x18000f805  mov     rdi, rbx
0x18000f808  nop     dword ptr [rax+rax+00000000h]
0x18000f810  inc     rdi
0x18000f813  cmp     word ptr [rsi+rdi*2], 0
0x18000f818  jnz     short loc_18000F810
0x18000f81a  mov     r15, r14
0x18000f81d  mov     [rsp+2C8h+var_290], r14
0x18000f822  lea     r14, [rdi+1]
0x18000f826  cmp     r14, rdi
0x18000f829  jb      loc_18000F995
0x18000f82f  mov     [rsp+2C8h+var_290], r15
0x18000f834  mov     eax, 2
0x18000f839  mul     r14
0x18000f83c  test    rdx, rdx
0x18000f83f  jnz     loc_18000F9A4
0x18000f845  mov     rcx, rax; cb
0x18000f848  call    cs:__imp_CoTaskMemAlloc
0x18000f84e  mov     r15, rax
0x18000f851  mov     [rsp+2C8h+var_290], rax
0x18000f856  xor     eax, eax
0x18000f858  mov     ebp, r13d
0x18000f85b  test    r15, r15
0x18000f85e  cmovnz  ebp, eax
0x18000f861  mov     r10, r15
0x18000f864  test    ebp, ebp
0x18000f866  js      loc_18000F8FF
0x18000f86c  test    r10, r10
0x18000f86f  jz      loc_18000FADF
0x18000f875  cmp     r14, 7FFFFFFFh
0x18000f87c  ja      loc_18000FAE8
0x18000f882  cmp     rdi, 7FFFFFFFh
0x18000f889  jnb     loc_18000F9B1
0x18000f88f  test    rsi, rsi
0x18000f892  jnz     short loc_18000F89D
0x18000f894  lea     rsi, pwzBaseUrl
0x18000f89b  xor     edi, edi
0x18000f89d  test    r14, r14
0x18000f8a0  jz      short loc_18000F8FF
0x18000f8a2  mov     rdx, r14
0x18000f8a5  mov     r8, r10
0x18000f8a8  xor     ecx, ecx
0x18000f8aa  nop     word ptr [rax+rax+00h]
0x18000f8b0  test    rdi, rdi
0x18000f8b3  jz      short loc_18000F8D5
0x18000f8b5  movzx   eax, word ptr [rsi]
0x18000f8b8  test    ax, ax
0x18000f8bb  jz      short loc_18000F8D5
0x18000f8bd  add     rsi, 2
0x18000f8c1  mov     [r8], ax
0x18000f8c5  add     r8, 2
0x18000f8c9  dec     rdi
0x18000f8cc  inc     rcx
0x18000f8cf  sub     rdx, 1
0x18000f8d3  jnz     short loc_18000F8B0
0x18000f8d5  lea     r9, [rcx-1]
0x18000f8d9  test    rdx, rdx
0x18000f8dc  cmovnz  r9, rcx
0x18000f8e0  lea     rcx, [r8-2]
0x18000f8e4  cmovnz  rcx, r8
0x18000f8e8  xor     eax, eax
0x18000f8ea  mov     [rcx], ax
0x18000f8ed  test    rdx, rdx
0x18000f8f0  jz      short loc_18000F8FF
0x18000f8f2  sub     r14, r9
0x18000f8f5  cmp     r14, 1
0x18000f8f9  ja      loc_18000FAF3
0x18000f8ff  mov     rcx, [rsp+2C8h+bstrString]; bstrString
0x18000f904  call    cs:__imp_SysFreeString
0x18000f90a  xor     r14d, r14d
0x18000f90d  mov     rcx, [rsp+2C8h+ppURI]
0x18000f912  test    rcx, rcx
0x18000f915  jz      short loc_18000F929
0x18000f917  mov     [rsp+2C8h+ppURI], r14
0x18000f91c  mov     rax, [rcx]
0x18000f91f  mov     rax, [rax+10h]
0x18000f923  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f928  nop
0x18000f929  test    ebp, ebp
0x18000f92b  js      short loc_18000F99F
0x18000f92d  mov     rcx, r15
0x18000f930  cmp     word ptr [r15], 5Ch ; '\'
0x18000f935  jnz     short loc_18000F93B
0x18000f937  add     rcx, 2; lpSrc
0x18000f93b  mov     r8d, 104h; nSize
0x18000f941  lea     rdx, [rsp+2C8h+Dst]; lpDst
0x18000f946  call    cs:__imp_ExpandEnvironmentStringsW
0x18000f94c  dec     eax
0x18000f94e  cmp     eax, 103h
0x18000f953  jbe     loc_18000FB18
0x18000f959  mov     r13d, 8007007Ah
0x18000f95f  test    r15, r15
0x18000f962  jz      short loc_18000F96E
0x18000f964  mov     rcx, r15; pv
0x18000f967  call    cs:__imp_CoTaskMemFree
0x18000f96d  nop
0x18000f96e  mov     eax, r13d
0x18000f971  mov     rcx, [rsp+2C8h+var_58]
0x18000f979  xor     rcx, rsp; StackCookie
0x18000f97c  call    __security_check_cookie
0x18000f981  add     rsp, 288h
0x18000f988  pop     r15
0x18000f98a  pop     r14
0x18000f98c  pop     r13
0x18000f98e  pop     r12
0x18000f990  pop     rdi
0x18000f991  pop     rsi
0x18000f992  pop     rbp
0x18000f993  pop     rbx
0x18000f994  retn
0x18000f995  mov     ebp, 80070216h
0x18000f99a  jmp     loc_18000F8FF
0x18000f99f  mov     r13d, ebp
0x18000f9a2  jmp     short loc_18000F95F
0x18000f9a4  xor     r10d, r10d
0x18000f9a7  mov     ebp, 80070216h
0x18000f9ac  jmp     loc_18000F864
0x18000f9b1  test    r14, r14
0x18000f9b4  jz      loc_18000F8FF
0x18000f9ba  xor     eax, eax
0x18000f9bc  mov     [r10], ax
0x18000f9c0  jmp     loc_18000F8FF
0x18000f9c5  mov     eax, 2
0x18000f9ca  mul     rdi
0x18000f9cd  test    rdx, rdx
0x18000f9d0  jnz     loc_18000FAA6
0x18000f9d6  mov     rcx, rax; cb
0x18000f9d9  call    cs:__imp_CoTaskMemAlloc
0x18000f9df  mov     r11, rax
0x18000f9e2  mov     [r12], rax
0x18000f9e6  test    rax, rax
0x18000f9e9  jnz     loc_18000FB1F
0x18000f9ef  test    r13d, r13d
0x18000f9f2  js      loc_18000F95F
0x18000f9f8  test    r11, r11
0x18000f9fb  jz      loc_18000FB27
0x18000fa01  cmp     rdi, 7FFFFFFFh
0x18000fa08  ja      loc_18000FB30
0x18000fa0e  cmp     rbx, 7FFFFFFFh
0x18000fa15  jnb     loc_18000FAB1
0x18000fa1b  test    rdi, rdi
0x18000fa1e  jz      loc_18000F95F
0x18000fa24  lea     rcx, [rsp+2C8h+Dst]
0x18000fa29  mov     rdx, rdi
0x18000fa2c  mov     r8, r11
0x18000fa2f  mov     r9, r14
0x18000fa32  test    rbx, rbx
0x18000fa35  jz      short loc_18000FA57
0x18000fa37  movzx   eax, word ptr [rcx]
0x18000fa3a  test    ax, ax
0x18000fa3d  jz      short loc_18000FA57
0x18000fa3f  add     rcx, 2
0x18000fa43  mov     [r8], ax
0x18000fa47  add     r8, 2
0x18000fa4b  dec     rbx
0x18000fa4e  inc     r9
0x18000fa51  sub     rdx, 1
0x18000fa55  jnz     short loc_18000FA32
0x18000fa57  lea     r10, [r9-1]
0x18000fa5b  test    rdx, rdx
0x18000fa5e  cmovnz  r10, r9
0x18000fa62  lea     rcx, [r8-2]
0x18000fa66  cmovnz  rcx, r8
0x18000fa6a  mov     [rcx], r14w
0x18000fa6e  jz      loc_18000F95F
0x18000fa74  sub     rdi, r10
0x18000fa77  cmp     rdi, 1
0x18000fa7b  jbe     loc_18000F95F
0x18000fa81  lea     r8, [rdi+rdi]
0x18000fa85  cmp     r8, 2
0x18000fa89  jbe     loc_18000F95F
0x18000fa8f  add     r8, 0FFFFFFFFFFFFFFFEh; Size
0x18000fa93  inc     r10
0x18000fa96  lea     rcx, [r11+r10*2]; void *
0x18000fa9a  xor     edx, edx; Val
0x18000fa9c  call    memset_0
0x18000faa1  jmp     loc_18000F95F
0x18000faa6  mov     r13d, 80070216h
0x18000faac  jmp     loc_18000F95F
0x18000fab1  test    rdi, rdi
0x18000fab4  jz      loc_18000F95F
0x18000faba  mov     [rax], r14w
0x18000fabe  jmp     loc_18000F95F
0x18000fac3  inc     rbx
0x18000fac6  cmp     word ptr [rcx+rbx*2], 0
0x18000facb  jnz     short loc_18000FAC3
0x18000facd  mov     [r12], r14
0x18000fad1  lea     rdi, [rbx+1]
0x18000fad5  cmp     rdi, rbx
0x18000fad8  jb      short loc_18000FAA6
0x18000fada  jmp     loc_18000F9C5
0x18000fadf  test    r14, r14
0x18000fae2  jz      loc_18000F875
0x18000fae8  xor     eax, eax
0x18000faea  mov     [r10], ax
0x18000faee  jmp     loc_18000F8FF
0x18000faf3  lea     r8, [r14+r14]
0x18000faf7  cmp     r8, 2
0x18000fafb  jbe     loc_18000F8FF
0x18000fb01  add     r8, 0FFFFFFFFFFFFFFFEh; Size
0x18000fb05  inc     r9
0x18000fb08  lea     rcx, [r10+r9*2]; void *
0x18000fb0c  xor     edx, edx; Val
0x18000fb0e  call    memset_0
0x18000fb13  jmp     loc_18000F8FF
0x18000fb18  lea     rcx, [rsp+2C8h+Dst]
0x18000fb1d  jmp     short loc_18000FAC3
0x18000fb1f  mov     r13d, r14d
0x18000fb22  jmp     loc_18000F9EF
0x18000fb27  test    rdi, rdi
0x18000fb2a  jz      loc_18000FA01
0x18000fb30  mov     [rax], r14w
0x18000fb34  jmp     loc_18000F95F
```
