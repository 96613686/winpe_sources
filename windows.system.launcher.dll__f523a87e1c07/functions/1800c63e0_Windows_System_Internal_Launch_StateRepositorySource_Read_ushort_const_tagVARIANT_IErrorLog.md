# Windows::System::Internal::Launch::StateRepositorySource::Read(ushort const *,tagVARIANT *,IErrorLog *)

- ea: `0x1800c63e0`
- end: `0x1800c65d7`
- name: `?Read@StateRepositorySource@Launch@Internal@System@Windows@@UEAAJPEBGPEAUtagVARIANT@@PEAUIErrorLog@@@Z`
- size: `503`
- prototype: `int(Windows::System::Internal::Launch::StateRepositorySource *__hidden this, const unsigned __int16 *, struct tagVARIANT *, struct IErrorLog *)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180023fcc`
- `0x1800c63e0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800c645c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800c6493`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800c64ca`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800c6503`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800c653a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800c6598`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800c645c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800c6493`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800c64ca`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800c6503`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800c653a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800c6598`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c655c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c655c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c6401`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c65c2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c6401`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c65c2`
- `OLEAUT32!__imp_SysAllocString` at `0x1800c6565`
- `OLEAUT32!__imp_SysAllocString` at `0x1800c6565`
- `OLEAUT32!__imp_VariantInit` at `0x1800c6428`
- `OLEAUT32!__imp_VariantInit` at `0x1800c646a`
- `OLEAUT32!__imp_VariantInit` at `0x1800c64a1`
- `OLEAUT32!__imp_VariantInit` at `0x1800c64d8`
- `OLEAUT32!__imp_VariantInit` at `0x1800c6511`
- `OLEAUT32!__imp_VariantInit` at `0x1800c6548`
- `OLEAUT32!__imp_VariantInit` at `0x1800c65a6`
- `OLEAUT32!__imp_VariantInit` at `0x1800c6428`
- `OLEAUT32!__imp_VariantInit` at `0x1800c646a`
- `OLEAUT32!__imp_VariantInit` at `0x1800c64a1`
- `OLEAUT32!__imp_VariantInit` at `0x1800c64d8`
- `OLEAUT32!__imp_VariantInit` at `0x1800c6511`
- `OLEAUT32!__imp_VariantInit` at `0x1800c6548`
- `OLEAUT32!__imp_VariantInit` at `0x1800c65a6`

## string_xrefs

- `0x1800c6441`: `ActivatableClassId`
- `0x1800c6486`: `ExtensionId`

## pseudocode

```c
__int64 __fastcall Windows::System::Internal::Launch::StateRepositorySource::Read(
        Windows::System::Internal::Launch::StateRepositorySource *this,
        const unsigned __int16 *a2,
        struct tagVARIANT *a3,
        struct IErrorLog *a4)
{
  __int64 v7; // rcx
  HSTRING v8; // rcx
  LONG v9; // eax
  const OLECHAR *StringRawBuffer; // rax
  BSTR v11; // rax
  unsigned int v12; // ebx
  HSTRING string; // [rsp+70h] [rbp+8h] BYREF

  string = 0;
  WindowsDeleteString(0);
  v7 = *((_QWORD *)this + 10);
  string = 0;
  if ( (int)LookupValueStringForKey(v7, a2, &string) < 0 )
  {
    if ( CompareStringOrdinal(a2, -1, L"ActivatableClassId", -1, 1) == 2 )
    {
      VariantInit(a3);
      a3->vt = 8;
      v8 = (HSTRING)*((_QWORD *)this + 13);
    }
    else
    {
      if ( CompareStringOrdinal(a2, -1, L"ExtensionId", -1, 1) != 2 )
      {
        if ( CompareStringOrdinal(a2, -1, L"DesiredInitialViewState", -1, 1) == 2 )
        {
          VariantInit(a3);
          a3->vt = 19;
          v9 = *((_DWORD *)this + 44);
        }
        else
        {
          if ( CompareStringOrdinal(a2, -1, L"PackageRelativeExecutable", -1, 1) == 2 )
          {
            VariantInit(a3);
            a3->vt = 8;
            v8 = (HSTRING)*((_QWORD *)this + 16);
            goto LABEL_13;
          }
          if ( CompareStringOrdinal(a2, -1, L"Parameters", -1, 1) == 2 )
          {
            VariantInit(a3);
            a3->vt = 8;
            v8 = (HSTRING)*((_QWORD *)this + 17);
            goto LABEL_13;
          }
          v12 = -2147024894;
          if ( CompareStringOrdinal(a2, -1, L"ExecutableIsNonPackaged", -1, 1) != 2 )
            goto LABEL_17;
          VariantInit(a3);
          a3->vt = 19;
          v9 = *((unsigned __int8 *)this + 181);
        }
        v12 = 0;
        a3->lVal = v9;
        goto LABEL_17;
      }
      VariantInit(a3);
      a3->vt = 8;
      v8 = (HSTRING)*((_QWORD *)this + 14);
    }
  }
  else
  {
    VariantInit(a3);
    v8 = string;
    a3->vt = 8;
  }
LABEL_13:
  StringRawBuffer = WindowsGetStringRawBuffer(v8, 0);
  v11 = SysAllocString(StringRawBuffer);
  a3->llVal = (LONGLONG)v11;
  v12 = v11 == 0 ? 0x8007000E : 0;
LABEL_17:
  WindowsDeleteString(string);
  return v12;
}

```

## disassembly

```asm
0x1800c63e0  push    rbx
0x1800c63e2  push    rbp
0x1800c63e3  push    rsi
0x1800c63e4  push    rdi
0x1800c63e5  push    r14
0x1800c63e7  push    r15
0x1800c63e9  sub     rsp, 38h
0x1800c63ed  mov     rbp, rcx
0x1800c63f0  mov     [rsp+68h+string], 0
0x1800c63f9  xor     ecx, ecx; string
0x1800c63fb  mov     rdi, r8
0x1800c63fe  mov     rsi, rdx
0x1800c6401  call    cs:__imp_WindowsDeleteString
0x1800c6407  mov     rcx, [rbp+50h]
0x1800c640b  lea     r8, [rsp+68h+string]
0x1800c6410  mov     rdx, rsi
0x1800c6413  mov     [rsp+68h+string], 0
0x1800c641c  call    ?LookupValueStringForKey@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEBGPEAPEAUHSTRING__@@@Z; LookupValueStringForKey(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ushort const *,HSTRING__ * *)
0x1800c6421  test    eax, eax
0x1800c6423  js      short loc_1800C643D
0x1800c6425  mov     rcx, rdi; pvarg
0x1800c6428  call    cs:__imp_VariantInit
0x1800c642e  mov     rcx, [rsp+68h+string]
0x1800c6433  mov     word ptr [rdi], 8
0x1800c6438  jmp     loc_1800C655A
0x1800c643d  or      r14d, 0FFFFFFFFh
0x1800c6441  lea     r8, aActivatablecla; "ActivatableClassId"
0x1800c6448  mov     r15d, 1
0x1800c644e  mov     r9d, r14d; cchCount2
0x1800c6451  mov     edx, r14d; cchCount1
0x1800c6454  mov     [rsp+68h+bIgnoreCase], r15d; bIgnoreCase
0x1800c6459  mov     rcx, rsi; lpString1
0x1800c645c  call    cs:__imp_CompareStringOrdinal
0x1800c6462  cmp     eax, 2
0x1800c6465  jnz     short loc_1800C647E
0x1800c6467  mov     rcx, rdi; pvarg
0x1800c646a  call    cs:__imp_VariantInit
0x1800c6470  mov     word ptr [rdi], 8
0x1800c6475  mov     rcx, [rbp+68h]
0x1800c6479  jmp     loc_1800C655A
0x1800c647e  mov     r9d, r14d; cchCount2
0x1800c6481  mov     [rsp+68h+bIgnoreCase], r15d; bIgnoreCase
0x1800c6486  lea     r8, aExtensionid; "ExtensionId"
0x1800c648d  mov     edx, r14d; cchCount1
0x1800c6490  mov     rcx, rsi; lpString1
0x1800c6493  call    cs:__imp_CompareStringOrdinal
0x1800c6499  cmp     eax, 2
0x1800c649c  jnz     short loc_1800C64B5
0x1800c649e  mov     rcx, rdi; pvarg
0x1800c64a1  call    cs:__imp_VariantInit
0x1800c64a7  mov     word ptr [rdi], 8
0x1800c64ac  mov     rcx, [rbp+70h]
0x1800c64b0  jmp     loc_1800C655A
0x1800c64b5  mov     r9d, r14d; cchCount2
0x1800c64b8  mov     [rsp+68h+bIgnoreCase], r15d; bIgnoreCase
0x1800c64bd  lea     r8, propName; "DesiredInitialViewState"
0x1800c64c4  mov     edx, r14d; cchCount1
0x1800c64c7  mov     rcx, rsi; lpString1
0x1800c64ca  call    cs:__imp_CompareStringOrdinal
0x1800c64d0  cmp     eax, 2
0x1800c64d3  jnz     short loc_1800C64EE
0x1800c64d5  mov     rcx, rdi; pvarg
0x1800c64d8  call    cs:__imp_VariantInit
0x1800c64de  mov     word ptr [rdi], 13h
0x1800c64e3  mov     eax, [rbp+0B0h]
0x1800c64e9  jmp     loc_1800C65B8
0x1800c64ee  mov     r9d, r14d; cchCount2
0x1800c64f1  mov     [rsp+68h+bIgnoreCase], r15d; bIgnoreCase
0x1800c64f6  lea     r8, aPackagerelativ_0; "PackageRelativeExecutable"
0x1800c64fd  mov     edx, r14d; cchCount1
0x1800c6500  mov     rcx, rsi; lpString1
0x1800c6503  call    cs:__imp_CompareStringOrdinal
0x1800c6509  cmp     eax, 2
0x1800c650c  jnz     short loc_1800C6525
0x1800c650e  mov     rcx, rdi; pvarg
0x1800c6511  call    cs:__imp_VariantInit
0x1800c6517  mov     word ptr [rdi], 8
0x1800c651c  mov     rcx, [rbp+80h]
0x1800c6523  jmp     short loc_1800C655A
0x1800c6525  mov     r9d, r14d; cchCount2
0x1800c6528  mov     [rsp+68h+bIgnoreCase], r15d; bIgnoreCase
0x1800c652d  lea     r8, aParameters; "Parameters"
0x1800c6534  mov     edx, r14d; cchCount1
0x1800c6537  mov     rcx, rsi; lpString1
0x1800c653a  call    cs:__imp_CompareStringOrdinal
0x1800c6540  cmp     eax, 2
0x1800c6543  jnz     short loc_1800C657E
0x1800c6545  mov     rcx, rdi; pvarg
0x1800c6548  call    cs:__imp_VariantInit
0x1800c654e  mov     word ptr [rdi], 8
0x1800c6553  mov     rcx, [rbp+88h]; string
0x1800c655a  xor     edx, edx; length
0x1800c655c  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c6562  mov     rcx, rax; psz
0x1800c6565  call    cs:__imp_SysAllocString
0x1800c656b  mov     [rdi+8], rax
0x1800c656f  neg     rax
0x1800c6572  sbb     ebx, ebx
0x1800c6574  not     ebx
0x1800c6576  and     ebx, 8007000Eh
0x1800c657c  jmp     short loc_1800C65BD
0x1800c657e  mov     r9d, r14d; cchCount2
0x1800c6581  mov     [rsp+68h+bIgnoreCase], r15d; bIgnoreCase
0x1800c6586  lea     r8, aExecutableisno; "ExecutableIsNonPackaged"
0x1800c658d  mov     edx, r14d; cchCount1
0x1800c6590  mov     rcx, rsi; lpString1
0x1800c6593  mov     ebx, 80070002h
0x1800c6598  call    cs:__imp_CompareStringOrdinal
0x1800c659e  cmp     eax, 2
0x1800c65a1  jnz     short loc_1800C65BD
0x1800c65a3  mov     rcx, rdi; pvarg
0x1800c65a6  call    cs:__imp_VariantInit
0x1800c65ac  mov     word ptr [rdi], 13h
0x1800c65b1  movzx   eax, byte ptr [rbp+0B5h]
0x1800c65b8  xor     ebx, ebx
0x1800c65ba  mov     [rdi+8], eax
0x1800c65bd  mov     rcx, [rsp+68h+string]; string
0x1800c65c2  call    cs:__imp_WindowsDeleteString
0x1800c65c8  mov     eax, ebx
0x1800c65ca  add     rsp, 38h
0x1800c65ce  pop     r15
0x1800c65d0  pop     r14
0x1800c65d2  pop     rdi
0x1800c65d3  pop     rsi
0x1800c65d4  pop     rbp
0x1800c65d5  pop     rbx
0x1800c65d6  retn
```
