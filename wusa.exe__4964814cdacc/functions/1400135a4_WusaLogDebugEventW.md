# WusaLogDebugEventW

- ea: `0x1400135a4`
- end: `0x14001383e`
- name: `WusaLogDebugEventW`
- size: `666`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140013490`

## callees

- `0x14000441c`
- `0x1400044e0`
- `0x1400135a4`
- `0x140014910`

## import_xrefs

- `ADVAPI32!EventEnabled` at `0x1400135f7`
- `ADVAPI32!EventEnabled` at `0x1400135f7`
- `ADVAPI32!EventWrite` at `0x14001380e`
- `ADVAPI32!EventWrite` at `0x14001380e`
- `KERNEL32!OutputDebugStringW` at `0x140013734`
- `KERNEL32!OutputDebugStringW` at `0x140013734`
- `msvcrt!_vsnwprintf` at `0x1400136e3`
- `msvcrt!_vsnwprintf` at `0x1400136e3`

## pseudocode

```c
__int64 WusaLogDebugEventW(__int64 a1, int a2, const wchar_t *a3, ...)
{
  signed int v5; // ecx
  __int64 v6; // rdx
  WCHAR *v7; // rax
  WCHAR *v8; // rsi
  unsigned __int64 v9; // rbx
  int v10; // eax
  unsigned __int64 v11; // rdi
  int v12; // eax
  unsigned __int64 v13; // rbx
  int v14; // eax
  WCHAR *v15; // rax
  int v16; // edx
  bool v17; // zf
  __int64 v19; // [rsp+38h] [rbp-890h]
  int v20; // [rsp+40h] [rbp-888h]
  int v21; // [rsp+48h] [rbp-880h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+78h] [rbp-850h] BYREF
  WCHAR OutputString[1024]; // [rsp+90h] [rbp-838h] BYREF
  va_list Args; // [rsp+8E8h] [rbp+20h] BYREF

  va_start(Args, a3);
  if ( !RegHandle || !EventEnabled(RegHandle, &WUSA_EVENT_DEBUG) )
    return 0;
  v5 = StringCchPrintfW(OutputString, 0x400u, L"%s.%05d: ", a1, a2);
  if ( v5 >= 0 )
  {
    v6 = 1024;
    v7 = OutputString;
    v5 = 0;
    while ( v6 && *v7 )
    {
      ++v7;
      --v6;
    }
    if ( !v6 )
      v5 = -2147024809;
    v19 = v5 < 0 ? 0LL : 1024 - v6;
    if ( v5 >= 0 )
    {
      v8 = &OutputString[v19];
      v9 = 1024 - v19;
      if ( 1024 == v19 || (v10 = 0, v9 > 0x7FFFFFFF) )
        v10 = -2147024809;
      if ( v10 < 0 )
      {
        if ( v9 )
          *v8 = 0;
      }
      else
      {
        v11 = v9 - 1;
        v12 = _vsnwprintf(v8, v9 - 1, a3, Args);
        if ( v12 < 0 || v12 > v11 )
        {
          v8[v11] = 0;
        }
        else if ( v12 == v11 )
        {
          v8[v11] = 0;
        }
      }
      StringCchCatW(v8, v9, L"\n");
      OutputDebugStringW(OutputString);
      v13 = v9 & 0x7FFFFFFFFFFFFFFFLL;
      v14 = 0;
      if ( v13 > 0x7FFFFFFF )
      {
        v5 = -2147024809;
      }
      else
      {
        v15 = OutputString;
        v5 = 0;
        v16 = v13;
        while ( 1 )
        {
          v17 = v13 == 0;
          if ( !v13 )
            break;
          if ( !*v15 )
          {
            v17 = v13 == 0;
            break;
          }
          ++v15;
          --v13;
        }
        if ( v17 )
          v5 = -2147024809;
        v21 = v5 < 0 ? 0 : v16 - v13;
        v14 = v21;
      }
      v20 = v5 < 0 ? 0 : 2 * v14;
      if ( v5 >= 0 )
      {
        UserData.Ptr = (ULONGLONG)OutputString;
        UserData.Size = v20 + 2;
        UserData.Reserved = 0;
        v5 = EventWrite(RegHandle, &WUSA_EVENT_DEBUG, 1u, &UserData);
        if ( v5 >= 0 )
          return 0;
      }
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1400135a4  mov     [rsp+Format], r8
0x1400135a9  mov     qword ptr [rsp+Args], r9
0x1400135ae  push    rbx
0x1400135af  push    rsi
0x1400135b0  push    rdi
0x1400135b1  push    r14
0x1400135b3  push    r15
0x1400135b5  sub     rsp, 8A0h
0x1400135bc  mov     rax, cs:__security_cookie
0x1400135c3  xor     rax, rsp
0x1400135c6  mov     [rsp+8C8h+var_38], rax
0x1400135ce  mov     edi, edx
0x1400135d0  mov     rbx, rcx
0x1400135d3  xor     r14d, r14d
0x1400135d6  mov     [rsp+8C8h+var_890], r14
0x1400135db  mov     [rsp+8C8h+var_888], r14
0x1400135e0  mov     rcx, cs:RegHandle; RegHandle
0x1400135e7  test    rcx, rcx
0x1400135ea  jz      loc_14001381A
0x1400135f0  lea     rdx, WUSA_EVENT_DEBUG; EventDescriptor
0x1400135f7  call    cs:__imp_EventEnabled
0x1400135fd  test    al, al
0x1400135ff  jz      loc_14001381A
0x140013605  mov     [rsp+8C8h+var_8A8], edi
0x140013609  mov     r9, rbx
0x14001360c  lea     r8, aS05d; "%s.%05d: "
0x140013613  mov     ebx, 400h
0x140013618  mov     edx, ebx; unsigned __int64
0x14001361a  lea     rcx, [rsp+8C8h+OutputString]; unsigned __int16 *
0x140013622  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140013627  mov     ecx, eax
0x140013629  test    eax, eax
0x14001362b  js      loc_14001381D
0x140013631  lea     r8, [rsp+8C8h+var_890]
0x140013636  mov     edx, ebx
0x140013638  mov     [rsp+8C8h+var_870], rbx
0x14001363d  lea     rax, [rsp+8C8h+OutputString]
0x140013645  mov     [rsp+8C8h+var_878], rax
0x14001364a  mov     ecx, r14d
0x14001364d  test    rdx, rdx
0x140013650  jz      short loc_14001366B
0x140013652  cmp     [rax], r14w
0x140013656  jz      short loc_14001366B
0x140013658  add     rax, 2
0x14001365c  mov     [rsp+8C8h+var_878], rax
0x140013661  dec     rdx
0x140013664  mov     [rsp+8C8h+var_870], rdx
0x140013669  jmp     short loc_14001364D
0x14001366b  mov     r15d, 80070057h
0x140013671  test    rdx, rdx
0x140013674  cmovz   ecx, r15d
0x140013678  test    ecx, ecx
0x14001367a  js      short loc_140013687
0x14001367c  mov     rax, rbx
0x14001367f  sub     rax, rdx
0x140013682  mov     [r8], rax
0x140013685  jmp     short loc_14001368A
0x140013687  mov     [r8], r14
0x14001368a  test    ecx, ecx
0x14001368c  jns     short loc_140013696
0x14001368e  mov     [r8], r14
0x140013691  jmp     loc_14001381D
0x140013696  mov     rax, [rsp+8C8h+var_890]
0x14001369b  lea     rsi, [rsp+8C8h+OutputString]
0x1400136a3  lea     rsi, [rsi+rax*2]
0x1400136a7  sub     rbx, rax
0x1400136aa  mov     [rsp+8C8h+var_890], rbx
0x1400136af  lea     r9, [rsp+8C8h+Args]; Args
0x1400136b7  jz      short loc_1400136C5
0x1400136b9  mov     eax, r14d
0x1400136bc  cmp     rbx, 7FFFFFFFh
0x1400136c3  jbe     short loc_1400136C8
0x1400136c5  mov     eax, r15d
0x1400136c8  test    eax, eax
0x1400136ca  js      short loc_14001370C
0x1400136cc  mov     [rsp+8C8h+var_898], r14d
0x1400136d1  lea     rdi, [rbx-1]
0x1400136d5  mov     r8, [rsp+8C8h+Format]; Format
0x1400136dd  mov     rdx, rdi; BufferCount
0x1400136e0  mov     rcx, rsi; Buffer
0x1400136e3  call    cs:__imp__vsnwprintf
0x1400136e9  test    eax, eax
0x1400136eb  js      short loc_1400136FD
0x1400136ed  cdqe
0x1400136ef  cmp     rax, rdi
0x1400136f2  ja      short loc_1400136FD
0x1400136f4  jnz     short loc_140013715
0x1400136f6  mov     [rsi+rdi*2], r14w
0x1400136fb  jmp     short loc_140013715
0x1400136fd  mov     [rsi+rdi*2], r14w
0x140013702  mov     [rsp+8C8h+var_898], 8007007Ah
0x14001370a  jmp     short loc_140013715
0x14001370c  test    rbx, rbx
0x14001370f  jz      short loc_140013715
0x140013711  mov     [rsi], r14w
0x140013715  mov     [rsp+8C8h+var_868], r14
0x14001371a  lea     r8, asc_140016DB8; "\n"
0x140013721  mov     rdx, rbx; unsigned __int64
0x140013724  mov     rcx, rsi; unsigned __int16 *
0x140013727  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14001372c  lea     rcx, [rsp+8C8h+OutputString]; lpOutputString
0x140013734  call    cs:__imp_OutputDebugStringW
0x14001373a  lea     r9, [rsp+8C8h+var_888]
0x14001373f  mov     rax, 7FFFFFFFFFFFFFFFh
0x140013749  and     rbx, rax
0x14001374c  mov     rax, r14
0x14001374f  mov     [rsp+8C8h+var_880], rax
0x140013754  cmp     rbx, 7FFFFFFFh
0x14001375b  ja      short loc_1400137B5
0x14001375d  lea     r8, [rsp+8C8h+var_880]
0x140013762  mov     [rsp+8C8h+var_858], rbx
0x140013767  lea     rax, [rsp+8C8h+OutputString]
0x14001376f  mov     [rsp+8C8h+var_860], rax
0x140013774  mov     ecx, r14d
0x140013777  mov     rdx, rbx
0x14001377a  test    rbx, rbx
0x14001377d  jz      short loc_14001379B
0x14001377f  cmp     [rax], r14w
0x140013783  jz      short loc_140013798
0x140013785  add     rax, 2
0x140013789  mov     [rsp+8C8h+var_860], rax
0x14001378e  dec     rbx
0x140013791  mov     [rsp+8C8h+var_858], rbx
0x140013796  jmp     short loc_14001377A
0x140013798  test    rbx, rbx
0x14001379b  cmovz   ecx, r15d
0x14001379f  test    ecx, ecx
0x1400137a1  js      short loc_1400137AB
0x1400137a3  sub     rdx, rbx
0x1400137a6  mov     [r8], rdx
0x1400137a9  jmp     short loc_1400137AE
0x1400137ab  mov     [r8], r14
0x1400137ae  mov     rax, [rsp+8C8h+var_880]
0x1400137b3  jmp     short loc_1400137B8
0x1400137b5  mov     ecx, r15d
0x1400137b8  test    ecx, ecx
0x1400137ba  js      short loc_1400137C4
0x1400137bc  add     rax, rax
0x1400137bf  mov     [r9], rax
0x1400137c2  jmp     short loc_1400137C7
0x1400137c4  mov     [r9], r14
0x1400137c7  test    ecx, ecx
0x1400137c9  js      short loc_14001381D
0x1400137cb  mov     rax, [rsp+8C8h+var_888]
0x1400137d0  add     rax, 2
0x1400137d4  mov     [rsp+8C8h+var_888], rax
0x1400137d9  lea     rcx, [rsp+8C8h+OutputString]
0x1400137e1  mov     [rsp+8C8h+UserData.Ptr], rcx
0x1400137e6  mov     [rsp+8C8h+UserData.Size], eax
0x1400137ed  mov     dword ptr [rsp+8C8h+UserData.0Ch], r14d
0x1400137f5  lea     r9, [rsp+8C8h+UserData]; UserData
0x1400137fa  mov     r8d, 1; UserDataCount
0x140013800  lea     rdx, WUSA_EVENT_DEBUG; EventDescriptor
0x140013807  mov     rcx, cs:RegHandle; RegHandle
0x14001380e  call    cs:__imp_EventWrite
0x140013814  mov     ecx, eax
0x140013816  test    eax, eax
0x140013818  js      short loc_14001381D
0x14001381a  mov     ecx, r14d
0x14001381d  mov     eax, ecx
0x14001381f  mov     rcx, [rsp+8C8h+var_38]
0x140013827  xor     rcx, rsp; StackCookie
0x14001382a  call    __security_check_cookie
0x14001382f  add     rsp, 8A0h
0x140013836  pop     r15
0x140013838  pop     r14
0x14001383a  pop     rdi
0x14001383b  pop     rsi
0x14001383c  pop     rbx
0x14001383d  retn
0x140014aac  push    rbp
0x140014aae  sub     rsp, 30h
0x140014ab2  mov     rbp, rdx
0x140014ab5  add     rsp, 30h
0x140014ab9  pop     rbp
0x140014aba  retn
```
