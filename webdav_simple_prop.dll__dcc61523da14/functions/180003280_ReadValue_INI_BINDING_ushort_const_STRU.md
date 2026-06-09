# ReadValue(INI_BINDING *,ushort const *,STRU *)

- ea: `0x180003280`
- end: `0x180003339`
- name: `?ReadValue@@YAJPEAUINI_BINDING@@PEBGPEAVSTRU@@@Z`
- size: `185`
- prototype: `__int64 __fastcall(LPCWSTR *, const unsigned __int16 *, struct STRU *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180001a04`
- `0x180002220`

## callees

- `0x180003280`

## import_xrefs

- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x180003324`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x180003324`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x1800032b1`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x18000330c`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x1800032b1`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x18000330c`
- `KERNEL32!GetPrivateProfileStringW` at `0x1800032de`
- `KERNEL32!GetPrivateProfileStringW` at `0x1800032de`

## pseudocode

```c
__int64 __fastcall ReadValue(LPCWSTR *a1, const unsigned __int16 *a2, struct STRU *a3)
{
  DWORD nSize; // edi
  int v7; // ebx
  unsigned int v8; // edx

  nSize = 256;
  **((_WORD **)a3 + 4) = 0;
  *((_DWORD *)a3 + 12) = 0;
  v7 = STRU::Resize(a3, 0x200u);
  if ( v7 >= 0 )
  {
    while ( 1 )
    {
      if ( GetPrivateProfileStringW(a1[11], a2, 0, *((LPWSTR *)a3 + 4), nSize, a1[4]) < nSize - 1 )
      {
        STRU::SyncWithBuffer(a3);
        return (unsigned int)v7;
      }
      v8 = 2 * nSize;
      if ( nSize >= 0x7FBC )
        break;
      if ( v8 <= 0x7FBC )
        goto LABEL_7;
      v8 = 32700;
      nSize = 32700;
LABEL_8:
      v7 = STRU::Resize(a3, 2 * v8);
      if ( v7 < 0 )
        return (unsigned int)v7;
    }
    if ( v8 > 0x7FBC )
      return (unsigned int)-2147024888;
LABEL_7:
    nSize *= 2;
    goto LABEL_8;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180003280  push    rbx
0x180003282  push    rbp
0x180003283  push    rsi
0x180003284  push    rdi
0x180003285  push    r14
0x180003287  push    r15
0x180003289  sub     rsp, 38h
0x18000328d  mov     r9, [r8+20h]
0x180003291  xor     eax, eax
0x180003293  mov     r14, rdx
0x180003296  mov     rbp, rcx
0x180003299  mov     edx, 200h
0x18000329e  mov     rcx, r8
0x1800032a1  mov     rsi, r8
0x1800032a4  mov     edi, 100h
0x1800032a9  mov     [r9], ax
0x1800032ad  mov     [r8+30h], eax
0x1800032b1  call    cs:__imp_?Resize@STRU@@QEAAJK@Z; STRU::Resize(ulong)
0x1800032b7  mov     ebx, eax
0x1800032b9  test    eax, eax
0x1800032bb  js      short loc_18000332A
0x1800032bd  mov     r15d, 7FBCh
0x1800032c3  mov     rcx, [rbp+20h]
0x1800032c7  xor     r8d, r8d; lpDefault
0x1800032ca  mov     r9, [rsi+20h]; lpReturnedString
0x1800032ce  mov     rdx, r14; lpKeyName
0x1800032d1  mov     [rsp+68h+lpFileName], rcx; lpFileName
0x1800032d6  mov     rcx, [rbp+58h]; lpAppName
0x1800032da  mov     [rsp+68h+nSize], edi; nSize
0x1800032de  call    cs:__imp_GetPrivateProfileStringW
0x1800032e4  lea     ecx, [rdi-1]
0x1800032e7  cmp     eax, ecx
0x1800032e9  jb      short loc_180003321
0x1800032eb  lea     edx, [rdi+rdi]
0x1800032ee  cmp     edi, r15d
0x1800032f1  jnb     short loc_180003300
0x1800032f3  cmp     edx, r15d
0x1800032f6  jbe     short loc_180003305
0x1800032f8  mov     edx, r15d
0x1800032fb  mov     edi, r15d
0x1800032fe  jmp     short loc_180003307
0x180003300  cmp     edx, r15d
0x180003303  ja      short loc_18000331A
0x180003305  mov     edi, edx
0x180003307  add     edx, edx
0x180003309  mov     rcx, rsi
0x18000330c  call    cs:__imp_?Resize@STRU@@QEAAJK@Z; STRU::Resize(ulong)
0x180003312  mov     ebx, eax
0x180003314  test    eax, eax
0x180003316  jns     short loc_1800032C3
0x180003318  jmp     short loc_18000332A
0x18000331a  mov     ebx, 80070008h
0x18000331f  jmp     short loc_18000332A
0x180003321  mov     rcx, rsi
0x180003324  call    cs:__imp_?SyncWithBuffer@STRU@@QEAAXXZ; STRU::SyncWithBuffer(void)
0x18000332a  mov     eax, ebx
0x18000332c  add     rsp, 38h
0x180003330  pop     r15
0x180003332  pop     r14
0x180003334  pop     rdi
0x180003335  pop     rsi
0x180003336  pop     rbp
0x180003337  pop     rbx
0x180003338  retn
```
