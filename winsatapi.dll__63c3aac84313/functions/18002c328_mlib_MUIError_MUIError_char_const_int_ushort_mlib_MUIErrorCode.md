# mlib::MUIError::MUIError(char const *,int,ushort,mlib::MUIErrorCode)

- ea: `0x18002c328`
- end: `0x18002c3c0`
- name: `??0MUIError@mlib@@QEAA@PEBDHGW4MUIErrorCode@1@@Z`
- size: `152`
- prototype: `__int64 __fastcall(__int64, __int64, int, __int16, int)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002c3c8`
- `0x18002c5d4`

## callees

- `0x18002c328`

## string_xrefs

- `0x18002c32c`: `base\winsat\api-dll\winsatcominterface.cpp`
- `0x18002c369`: `a MUIError was created incorrectly`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall mlib::MUIError::MUIError(__int64 a1, __int64 a2, int a3, __int16 a4, int a5)
{
  const wchar_t *v5; // rax

  *(_QWORD *)a1 = "base\\winsat\\api-dll\\winsatcominterface.cpp";
  *(_DWORD *)(a1 + 8) = a3;
  *(_WORD *)(a1 + 12) = a4;
  *(_DWORD *)(a1 + 16) = a5;
  if ( a5 )
  {
    switch ( a5 )
    {
      case 1:
        v5 = L"resource ID does not exist";
        break;
      case 2:
        v5 = L"cannot get the size of the string";
        break;
      case 3:
        v5 = L"cannot load the resource";
        break;
      case 4:
        v5 = L"cannot lock the resource";
        break;
      case 5:
        v5 = L"the string is zero length";
        break;
      case 6:
        v5 = L"the string is not null terminated";
        break;
      case 7:
        v5 = L"string formatting error";
        break;
      default:
        v5 = L"a MUIError was created incorrectly";
        break;
    }
  }
  else
  {
    v5 = L"MUI string loader sub-system not initilized";
  }
  *(_QWORD *)(a1 + 24) = v5;
  return a1;
}

```

## disassembly

```asm
0x18002c328  mov     edx, [rsp+arg_20]
0x18002c32c  lea     rax, aBaseWinsatApiD; "base\\winsat\\api-dll\\winsatcominterfa"...
0x18002c333  mov     [rcx], rax
0x18002c336  mov     [rcx+8], r8d
0x18002c33a  mov     [rcx+0Ch], r9w
0x18002c33f  mov     [rcx+10h], edx
0x18002c342  test    edx, edx
0x18002c344  jz      short loc_18002C3B1
0x18002c346  sub     edx, 1
0x18002c349  jz      short loc_18002C3A8
0x18002c34b  sub     edx, 1
0x18002c34e  jz      short loc_18002C39F
0x18002c350  sub     edx, 1
0x18002c353  jz      short loc_18002C396
0x18002c355  sub     edx, 1
0x18002c358  jz      short loc_18002C38D
0x18002c35a  sub     edx, 1
0x18002c35d  jz      short loc_18002C384
0x18002c35f  sub     edx, 1
0x18002c362  jz      short loc_18002C37B
0x18002c364  cmp     edx, 1
0x18002c367  jz      short loc_18002C372
0x18002c369  lea     rax, aAMuierrorWasCr; "a MUIError was created incorrectly"
0x18002c370  jmp     short loc_18002C3B8
0x18002c372  lea     rax, aStringFormatti; "string formatting error"
0x18002c379  jmp     short loc_18002C3B8
0x18002c37b  lea     rax, aTheStringIsNot; "the string is not null terminated"
0x18002c382  jmp     short loc_18002C3B8
0x18002c384  lea     rax, aTheStringIsZer; "the string is zero length"
0x18002c38b  jmp     short loc_18002C3B8
0x18002c38d  lea     rax, aCannotLockTheR; "cannot lock the resource"
0x18002c394  jmp     short loc_18002C3B8
0x18002c396  lea     rax, aCannotLoadTheR; "cannot load the resource"
0x18002c39d  jmp     short loc_18002C3B8
0x18002c39f  lea     rax, aCannotGetTheSi; "cannot get the size of the string"
0x18002c3a6  jmp     short loc_18002C3B8
0x18002c3a8  lea     rax, aResourceIdDoes; "resource ID does not exist"
0x18002c3af  jmp     short loc_18002C3B8
0x18002c3b1  lea     rax, aMuiStringLoade; "MUI string loader sub-system not initil"...
0x18002c3b8  mov     [rcx+18h], rax
0x18002c3bc  mov     rax, rcx
0x18002c3bf  retn
```
