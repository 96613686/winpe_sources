# CreateTempStreamName

- ea: `0x180030750`
- end: `0x180030807`
- name: `CreateTempStreamName`
- size: `183`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180030584`

## callees

- `0x180030638`
- `0x180030750`
- `0x180030810`
- `0x180030884`
- `0x18003095c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800307bc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800307bc`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x1800307e1`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x1800307e1`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1800307d0`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1800307d0`

## pseudocode

```c
__int64 __fastcall CreateTempStreamName(unsigned __int16 *a1, __int64 a2, unsigned __int16 *a3, unsigned int a4)
{
  unsigned __int64 v5; // rbp
  int v6; // edi
  int v7; // r11d
  const unsigned __int16 *v8; // r8
  unsigned __int16 *v9; // rbx
  int v10; // eax
  LPWSTR ExtensionW; // rax
  unsigned __int16 *v13; // [rsp+20h] [rbp-38h] BYREF

  v5 = a4;
  v6 = StringCchCopyW(a3, a4, a1);
  if ( v6 >= 0 )
  {
    if ( v7 )
    {
      v8 = L".~tmp";
    }
    else
    {
      *PathFindFileNameW(a3) = 126;
      ExtensionW = PathFindExtensionW(a3);
      v8 = L".tmp";
      *ExtensionW = 0;
    }
    v6 = StringCchCatW(a3, v5, v8);
    if ( v6 >= 0 )
    {
      v9 = 0;
      v13 = 0;
      if ( !(unsigned __int8)anonymous_namespace_::RtlAreLongPathsEnabled() )
      {
        v10 = AddExtendedLengthPathNotationIfNeeded(a3, &v13);
        v9 = v13;
        if ( v10 >= 0 )
          v6 = StringCchCopyW(a3, v5, v13);
      }
      LocalFree(v9);
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180030750  push    rbx
0x180030752  push    rbp
0x180030753  push    rsi
0x180030754  push    rdi
0x180030755  sub     rsp, 38h
0x180030759  mov     rsi, r8
0x18003075c  mov     ebp, r9d
0x18003075f  mov     r8, rcx; unsigned __int16 *
0x180030762  mov     r11d, edx
0x180030765  mov     rcx, rsi; unsigned __int16 *
0x180030768  mov     edx, r9d; unsigned __int64
0x18003076b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180030770  mov     edi, eax
0x180030772  test    eax, eax
0x180030774  js      short loc_1800307C2
0x180030776  test    r11d, r11d
0x180030779  jz      short loc_1800307CD
0x18003077b  lea     r8, aTmp_0; ".~tmp"
0x180030782  mov     rdx, rbp; unsigned __int64
0x180030785  mov     rcx, rsi; unsigned __int16 *
0x180030788  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003078d  mov     edi, eax
0x18003078f  test    eax, eax
0x180030791  js      short loc_1800307C2
0x180030793  xor     ebx, ebx
0x180030795  mov     [rsp+58h+var_38], rbx
0x18003079a  call    _anonymous_namespace___RtlAreLongPathsEnabled
0x18003079f  test    al, al
0x1800307a1  jnz     short loc_1800307B9
0x1800307a3  lea     rdx, [rsp+58h+var_38]; unsigned __int16 **
0x1800307a8  mov     rcx, rsi; unsigned __int16 *
0x1800307ab  call    ?AddExtendedLengthPathNotationIfNeeded@@YAJPEBGPEAPEAG@Z; AddExtendedLengthPathNotationIfNeeded(ushort const *,ushort * *)
0x1800307b0  mov     rbx, [rsp+58h+var_38]
0x1800307b5  test    eax, eax
0x1800307b7  jns     short loc_1800307F5
0x1800307b9  mov     rcx, rbx; hMem
0x1800307bc  call    cs:__imp_LocalFree
0x1800307c2  mov     eax, edi
0x1800307c4  add     rsp, 38h
0x1800307c8  pop     rdi
0x1800307c9  pop     rsi
0x1800307ca  pop     rbp
0x1800307cb  pop     rbx
0x1800307cc  retn
0x1800307cd  mov     rcx, rsi; pszPath
0x1800307d0  call    cs:__imp_PathFindFileNameW
0x1800307d6  mov     ecx, 7Eh ; '~'
0x1800307db  mov     [rax], cx
0x1800307de  mov     rcx, rsi; pszPath
0x1800307e1  call    cs:__imp_PathFindExtensionW
0x1800307e7  xor     ecx, ecx
0x1800307e9  lea     r8, aTmp; ".tmp"
0x1800307f0  mov     [rax], cx
0x1800307f3  jmp     short loc_180030782
0x1800307f5  mov     r8, rbx; unsigned __int16 *
0x1800307f8  mov     rdx, rbp; unsigned __int64
0x1800307fb  mov     rcx, rsi; unsigned __int16 *
0x1800307fe  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180030803  mov     edi, eax
0x180030805  jmp     short loc_1800307B9
```
