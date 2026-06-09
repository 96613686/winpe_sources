# p9fs::File::ConvertPath(std::basic_string_view<char,std::char_traits<char>>)

- ea: `0x18001e5f0`
- end: `0x18001e728`
- name: `?ConvertPath@File@p9fs@@CA?AV?$BasicExpected@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@J@util@@V?$basic_string_view@DU?$char_traits@D@std@@@std@@@Z`
- size: `312`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path`

## callers

- `0x1800218b0`

## callees

- `0x180004120`
- `0x180004c98`
- `0x18001d8b4`
- `0x18001d940`
- `0x18001dc10`
- `0x18001e5f0`
- `0x18001ff4c`

## import_xrefs

- `lxutil!LxUtilNtPathEscapeInPlace` at `0x18001e69d`
- `lxutil!LxUtilNtPathEscapeInPlace` at `0x18001e69d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall p9fs::File::ConvertPath(__int64 a1, __int64 a2)
{
  unsigned __int64 v3; // r8
  __int64 v4; // rax
  __int128 *v5; // rdx
  __int128 pExceptionObject; // [rsp+28h] [rbp-58h] BYREF
  __int64 v8; // [rsp+38h] [rbp-48h]
  __int128 v9; // [rsp+48h] [rbp-38h] BYREF
  __int128 v10; // [rsp+58h] [rbp-28h]
  _QWORD v11[2]; // [rsp+68h] [rbp-18h] BYREF

  v11[0] = a1;
  v9 = 0;
  *(_QWORD *)&v10 = 0;
  *((_QWORD *)&v10 + 1) = 7;
  LOWORD(v9) = 0;
  v3 = *(_QWORD *)(a2 + 8);
  if ( v3 )
  {
    if ( v3 > 0x1000 )
    {
      *(_BYTE *)a1 = 0;
      *(_DWORD *)(a1 + 8) = -36;
      goto LABEL_8;
    }
    v4 = Vml::MultiByteToWide(&pExceptionObject, *(LPCCH *)a2, v3);
    std::wstring::operator=(&v9, v4);
    std::wstring::~wstring(&pExceptionObject);
    v5 = &v9;
    if ( *((_QWORD *)&v10 + 1) > 7u )
      v5 = (__int128 *)v9;
    if ( (unsigned __int16)(2 * v10) != 2LL * (_QWORD)v10 )
    {
      pExceptionObject = 0;
      v8 = 0;
      gsl::narrowing_error::narrowing_error((gsl::narrowing_error *)&pExceptionObject);
      throw (gsl::narrowing_error *)&pExceptionObject;
    }
    LOWORD(v11[0]) = 2 * v10;
    WORD1(v11[0]) = 2 * v10;
    HIDWORD(v11[0]) = 0;
    v11[1] = v5;
    LxUtilNtPathEscapeInPlace(v11, 0);
  }
  *(_BYTE *)a1 = 1;
  *(_OWORD *)(a1 + 8) = v9;
  *(_OWORD *)(a1 + 24) = v10;
  *(_QWORD *)&v10 = 0;
  *((_QWORD *)&v10 + 1) = 7;
  LOWORD(v9) = 0;
LABEL_8:
  std::wstring::~wstring(&v9);
  return a1;
}

```

## disassembly

```asm
0x18001e5f0  mov     [rsp-8+arg_10], rbx
0x18001e5f5  push    rbp
0x18001e5f6  mov     rbp, rsp
0x18001e5f9  sub     rsp, 80h
0x18001e600  mov     rax, cs:__security_cookie
0x18001e607  xor     rax, rsp
0x18001e60a  mov     [rbp+var_8], rax
0x18001e60e  mov     rbx, rcx
0x18001e611  mov     [rbp+var_18], rcx
0x18001e615  xorps   xmm0, xmm0
0x18001e618  movups  [rbp+var_38], xmm0
0x18001e61c  mov     qword ptr [rbp+var_28], 0
0x18001e624  mov     qword ptr [rbp+var_28+8], 7
0x18001e62c  xor     eax, eax
0x18001e62e  mov     word ptr [rbp+var_38], ax
0x18001e632  mov     r8, [rdx+8]; cbMultiByte
0x18001e636  test    r8, r8
0x18001e639  jz      short loc_18001E6A3
0x18001e63b  cmp     r8, 1000h
0x18001e642  ja      loc_18001E6F5
0x18001e648  mov     rdx, [rdx]; lpMultiByteStr
0x18001e64b  lea     rcx, [rbp+pExceptionObject]; Src
0x18001e64f  call    ?MultiByteToWide@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBD_KI@Z; Vml::MultiByteToWide(char const *,unsigned __int64,uint)
0x18001e654  mov     rdx, rax
0x18001e657  lea     rcx, [rbp+var_38]
0x18001e65b  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18001e660  lea     rcx, [rbp+pExceptionObject]
0x18001e664  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001e669  lea     rdx, [rbp+var_38]
0x18001e66d  cmp     qword ptr [rbp+var_28+8], 7
0x18001e672  cmova   rdx, qword ptr [rbp+var_38]
0x18001e677  mov     rax, qword ptr [rbp+var_28]
0x18001e67b  add     rax, rax
0x18001e67e  movzx   ecx, ax
0x18001e681  cmp     rcx, rax
0x18001e684  jnz     short loc_18001E701
0x18001e686  xor     eax, eax
0x18001e688  mov     word ptr [rbp+var_18], cx
0x18001e68c  mov     word ptr [rbp+var_18+2], cx
0x18001e690  mov     dword ptr [rbp+var_18+4], eax
0x18001e693  mov     [rbp+var_10], rdx
0x18001e697  xor     edx, edx
0x18001e699  lea     rcx, [rbp+var_18]
0x18001e69d  call    cs:__imp_LxUtilNtPathEscapeInPlace
0x18001e6a3  mov     byte ptr [rbx], 1
0x18001e6a6  movups  xmm0, [rbp+var_38]
0x18001e6aa  movups  xmmword ptr [rbx+8], xmm0
0x18001e6ae  movups  xmm1, [rbp+var_28]
0x18001e6b2  movups  xmmword ptr [rbx+18h], xmm1
0x18001e6b6  mov     qword ptr [rbp+var_28], 0
0x18001e6be  mov     qword ptr [rbp+var_28+8], 7
0x18001e6c6  xor     eax, eax
0x18001e6c8  mov     word ptr [rbp+var_38], ax
0x18001e6cc  lea     rcx, [rbp+var_38]
0x18001e6d0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001e6d5  mov     rax, rbx
0x18001e6d8  mov     rcx, [rbp+var_8]
0x18001e6dc  xor     rcx, rsp; StackCookie
0x18001e6df  call    __security_check_cookie
0x18001e6e4  mov     rbx, [rsp+80h+arg_10]
0x18001e6ec  add     rsp, 80h
0x18001e6f3  pop     rbp
0x18001e6f4  retn
0x18001e6f5  mov     byte ptr [rcx], 0
0x18001e6f8  mov     dword ptr [rcx+8], 0FFFFFFDCh
0x18001e6ff  jmp     short loc_18001E6CC
0x18001e701  xorps   xmm0, xmm0
0x18001e704  xor     eax, eax
0x18001e706  movups  [rbp+pExceptionObject], xmm0
0x18001e70a  mov     [rbp+var_48], rax
0x18001e70e  lea     rcx, [rbp+pExceptionObject]; this
0x18001e712  call    ??0narrowing_error@gsl@@QEAA@XZ; gsl::narrowing_error::narrowing_error(void)
0x18001e717  lea     rdx, _TI2?AUnarrowing_error@gsl@@; pThrowInfo
0x18001e71e  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001e722  call    _CxxThrowException_0
```
