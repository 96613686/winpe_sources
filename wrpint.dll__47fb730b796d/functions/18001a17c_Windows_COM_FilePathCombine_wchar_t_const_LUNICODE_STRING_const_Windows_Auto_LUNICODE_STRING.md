# Windows::COM::FilePathCombine(wchar_t const *,_LUNICODE_STRING const &,Windows::Auto<_LUNICODE_STRING> *)

- ea: `0x18001a17c`
- end: `0x18001a257`
- name: `?FilePathCombine@COM@Windows@@YAJPEB_WAEBU_LUNICODE_STRING@@PEAV?$Auto@U_LUNICODE_STRING@@@2@@Z`
- size: `219`
- prototype: `__int64 __fastcall(__int64, __int128 *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callers

- `0x18001a260`

## callees

- `0x180007568`
- `0x180007cc0`
- `0x18001a17c`
- `0x18001a5e4`
- `0x18001b30c`

## string_xrefs

- `0x18001a18c`: `onecore\base\wcp\rtllib\win32lib\dllpath_library.cpp`
- `0x18001a1a5`: `Windows::COM::FilePathCombine`

## pseudocode

```c
__int64 __fastcall Windows::COM::FilePathCombine(__int64 a1, __int128 *a2, unsigned __int64 *a3)
{
  __int64 result; // rax
  __int128 v5; // xmm0
  __int64 v6; // xmm1_8
  NTSTATUS v7; // eax
  unsigned __int64 v8; // rcx
  __int128 v9; // [rsp+20h] [rbp-38h] BYREF
  __int64 v10; // [rsp+30h] [rbp-28h]
  __int64 v11; // [rsp+38h] [rbp-20h]
  __int64 v12; // [rsp+40h] [rbp-18h]
  const wchar_t *v13; // [rsp+48h] [rbp-10h]

  if ( !a3 )
  {
    v10 = 112;
    *(_QWORD *)&v9 = "onecore\\base\\wcp\\rtllib\\win32lib\\dllpath_library.cpp";
    *((_QWORD *)&v9 + 1) = "Windows::COM::FilePathCombine";
    v11 = (__int64)"Not-null check failed: FullFileName";
    RtlReportErrorOrigination(a1, a2, 2147500035LL);
    return 2147500035LL;
  }
  v5 = *a2;
  v11 = 8;
  v6 = *((_QWORD *)a2 + 2);
  v9 = v5;
  v12 = 10;
  v10 = v6;
  v13 = L"\\\\?\\";
  v7 = RtlCombineNtPathSegments(a1, &v9);
  if ( v7 < 0 )
    return ConvertNtStatusToHResult(v7);
  v8 = *a3;
  if ( a3[1] - *a3 >= 2 )
    goto LABEL_10;
  if ( v8 + 2 < v8 )
    return ConvertNtStatusToHResult(-1073741675);
  v7 = RtlReallocateLUnicodeString(v8, v8 + 2, a3);
  if ( v7 < 0 )
    return ConvertNtStatusToHResult(v7);
LABEL_10:
  result = 0;
  *(_WORD *)(a3[2] + 2 * (*a3 >> 1)) = 0;
  return result;
}

```

## disassembly

```asm
0x18001a17c  mov     r11, rsp
0x18001a17f  push    rbx
0x18001a180  sub     rsp, 50h
0x18001a184  mov     rbx, r8
0x18001a187  test    r8, r8
0x18001a18a  jnz     short loc_18001A1CA
0x18001a18c  lea     rax, aOnecoreBaseWcp; "onecore\\base\\wcp\\rtllib\\win32lib\\d"...
0x18001a193  mov     qword ptr [r11-28h], 70h ; 'p'
0x18001a19b  mov     [r11-38h], rax
0x18001a19f  mov     r8d, 80004003h
0x18001a1a5  lea     rax, aWindowsComFile; "Windows::COM::FilePathCombine"
0x18001a1ac  mov     [r11-30h], rax
0x18001a1b0  lea     rax, aNotNullCheckFa_4; "Not-null check failed: FullFileName"
0x18001a1b7  mov     [r11-20h], rax
0x18001a1bb  call    RtlReportErrorOrigination
0x18001a1c0  mov     eax, 80004003h
0x18001a1c5  jmp     loc_18001A251
0x18001a1ca  movups  xmm0, xmmword ptr [rdx]
0x18001a1cd  lea     rax, Buf2; "\\\\?\\"
0x18001a1d4  mov     [rsp+58h+var_20], 8
0x18001a1dd  movsd   xmm1, qword ptr [rdx+10h]
0x18001a1e2  lea     rdx, [rsp+58h+var_38]
0x18001a1e7  movups  [rsp+58h+var_38], xmm0
0x18001a1ec  mov     [rsp+58h+var_18], 0Ah
0x18001a1f5  movsd   [rsp+58h+var_28], xmm1
0x18001a1fb  mov     [rsp+58h+var_10], rax
0x18001a200  call    RtlCombineNtPathSegments
0x18001a205  test    eax, eax
0x18001a207  js      short loc_18001A235
0x18001a209  mov     rcx, [rbx]
0x18001a20c  mov     rax, [rbx+8]
0x18001a210  sub     rax, rcx
0x18001a213  cmp     rax, 2
0x18001a217  jnb     short loc_18001A241
0x18001a219  lea     rdx, [rcx+2]
0x18001a21d  cmp     rdx, rcx
0x18001a220  jnb     short loc_18001A229
0x18001a222  mov     eax, 0C0000095h
0x18001a227  jmp     short loc_18001A235
0x18001a229  mov     r8, rbx
0x18001a22c  call    RtlReallocateLUnicodeString
0x18001a231  test    eax, eax
0x18001a233  jns     short loc_18001A241
0x18001a235  mov     ecx, eax; Status
0x18001a237  add     rsp, 50h
0x18001a23b  pop     rbx
0x18001a23c  jmp     ConvertNtStatusToHResult
0x18001a241  mov     rdx, [rbx]
0x18001a244  mov     rcx, [rbx+10h]
0x18001a248  shr     rdx, 1
0x18001a24b  xor     eax, eax
0x18001a24d  mov     [rcx+rdx*2], ax
0x18001a251  add     rsp, 50h
0x18001a255  pop     rbx
0x18001a256  retn
```
