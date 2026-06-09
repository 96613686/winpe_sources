# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)

- ea: `0x18000acf0`
- end: `0x18000aef9`
- name: `?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ`
- size: `521`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000a490`
- `0x18001c190`
- `0x180091960`
- `0x180096e3c`

## callees

- `0x18000acf0`
- `0x18000af00`
- `0x180054ae0`
- `0x1800620d0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__set_errno` at `0x18000ae23`
- `api-ms-win-crt-private-l1-1-0!_o__set_errno` at `0x18000ae23`
- `api-ms-win-crt-private-l1-1-0!_o__get_errno` at `0x18000ae9d`
- `api-ms-win-crt-private-l1-1-0!_o__get_errno` at `0x18000ae9d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ad73`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ad73`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000adf9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000adf9`

## pseudocode

```c
__int64 Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
        __int64 a1,
        const wchar_t *a2,
        ...)
{
  unsigned __int64 v3; // rcx
  unsigned __int64 v5; // rsi
  unsigned __int64 v6; // r8
  _WORD *v7; // rax
  int v8; // ebx
  unsigned __int64 v10; // rbx
  LPVOID v11; // rax
  unsigned __int64 v12; // rsi
  wchar_t *v13; // r14
  size_t v14; // rsi
  int v15; // eax
  unsigned __int64 v16; // rax
  _QWORD v17[7]; // [rsp+20h] [rbp-38h] BYREF
  va_list Args; // [rsp+70h] [rbp+18h] BYREF

  va_start(Args, a2);
  v17[0] = 0;
  v3 = 32;
  while ( 1 )
  {
    v5 = v3 + 1;
    if ( v3 + 1 < v3 )
    {
LABEL_39:
      v8 = -2147024362;
      goto LABEL_40;
    }
    v6 = *(_QWORD *)(a1 + 16);
    if ( v6 == -1 )
    {
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCount(a1);
      if ( *(_QWORD *)a1 )
        v6 = *(_QWORD *)(a1 + 8) + 1LL;
      else
        v6 = 0;
      *(_QWORD *)(a1 + 16) = v6;
    }
    if ( v6 )
    {
      if ( v5 > v6 )
      {
        v17[0] = 0;
        v10 = 2 * v6;
        if ( !is_mul_ok(v6, 2u) )
          goto LABEL_39;
        if ( v6 > 0x800 )
          v10 = v6 + 2048;
        if ( v5 > v10 )
          v10 = v5;
        v11 = CoTaskMemRealloc(*(LPVOID *)a1, 2 * v10);
        if ( !v11 )
        {
          v8 = -2147024882;
          goto LABEL_40;
        }
        *(_QWORD *)(a1 + 16) = v10;
        *(_QWORD *)a1 = v11;
      }
    }
    else
    {
      v17[0] = 0;
      if ( !is_mul_ok(v5, 2u) )
        goto LABEL_39;
      v7 = CoTaskMemAlloc(2 * v5);
      if ( v7 )
      {
        v8 = 0;
        *(_QWORD *)(a1 + 16) = v5;
        *(_QWORD *)a1 = v7;
        *v7 = 0;
      }
      else
      {
        v8 = -2147024882;
      }
      if ( v8 < 0 )
        goto LABEL_14;
    }
    v12 = *(_QWORD *)(a1 + 16);
    v13 = *(wchar_t **)a1;
    _o__set_errno(0);
    if ( v12 )
      break;
    v8 = -2147024809;
LABEL_32:
    if ( v8 != -2147024774 )
      goto LABEL_40;
    LODWORD(v17[0]) = 0;
    _o__get_errno(v17);
    if ( LODWORD(v17[0]) == 22 )
      goto LABEL_38;
    v16 = *(_QWORD *)(a1 + 16);
    v3 = v16 + 32;
    if ( v16 + 32 < v16 )
    {
      v8 = -2147024362;
LABEL_14:
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(a1);
      return (unsigned int)v8;
    }
  }
  if ( v12 <= 0x7FFFFFFF )
  {
    v14 = v12 - 1;
    v15 = vsnwprintf(v13, v14, a2, Args);
    if ( v15 < 0 || v15 > v14 )
    {
      v8 = -2147024774;
      v13[v14] = 0;
    }
    else
    {
      v8 = 0;
      if ( v15 == v14 )
        v13[v14] = 0;
    }
    goto LABEL_32;
  }
  *v13 = 0;
LABEL_38:
  v8 = -2147024809;
LABEL_40:
  if ( v8 < 0 )
    goto LABEL_14;
  *(_QWORD *)(a1 + 8) = -1;
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000acf0  mov     rax, rsp
0x18000acf3  mov     [rax+10h], rdx
0x18000acf7  mov     [rax+18h], r8
0x18000acfb  mov     [rax+20h], r9
0x18000acff  push    rbx
0x18000ad00  push    rbp
0x18000ad01  push    rsi
0x18000ad02  push    rdi
0x18000ad03  push    r14
0x18000ad05  sub     rsp, 30h
0x18000ad09  mov     rdi, rcx
0x18000ad0c  mov     qword ptr [rax-38h], 0
0x18000ad14  mov     ecx, 20h ; ' '
0x18000ad19  mov     rbp, rdx
0x18000ad1c  lea     rsi, [rcx+1]
0x18000ad20  lea     rbx, [rsp+58h+Args]
0x18000ad25  cmp     rsi, rcx
0x18000ad28  jb      loc_18000AEDF
0x18000ad2e  mov     r8, [rdi+10h]
0x18000ad32  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18000ad36  jnz     short loc_18000AD56
0x18000ad38  mov     rcx, rdi
0x18000ad3b  call    ?_EnsureCount@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCount(void)
0x18000ad40  cmp     qword ptr [rdi], 0
0x18000ad44  jz      short loc_18000AD4F
0x18000ad46  mov     r8, [rdi+8]
0x18000ad4a  inc     r8
0x18000ad4d  jmp     short loc_18000AD52
0x18000ad4f  xor     r8d, r8d
0x18000ad52  mov     [rdi+10h], r8
0x18000ad56  test    r8, r8
0x18000ad59  jnz     short loc_18000ADB3
0x18000ad5b  lea     eax, [r8+2]
0x18000ad5f  mov     [rsp+58h+var_38], r8
0x18000ad64  mul     rsi
0x18000ad67  test    rdx, rdx
0x18000ad6a  jnz     loc_18000AEDF
0x18000ad70  mov     rcx, rax; cb
0x18000ad73  call    cs:__imp_CoTaskMemAlloc
0x18000ad7a  nop     dword ptr [rax+rax+00h]
0x18000ad7f  test    rax, rax
0x18000ad82  jz      short loc_18000AD94
0x18000ad84  xor     ebx, ebx
0x18000ad86  mov     [rdi+10h], rsi
0x18000ad8a  xor     ecx, ecx
0x18000ad8c  mov     [rdi], rax
0x18000ad8f  mov     [rax], cx
0x18000ad92  jmp     short loc_18000AD99
0x18000ad94  mov     ebx, 8007000Eh
0x18000ad99  test    ebx, ebx
0x18000ad9b  jns     short loc_18000AE15
0x18000ad9d  mov     rcx, rdi
0x18000ada0  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18000ada5  mov     eax, ebx
0x18000ada7  add     rsp, 30h
0x18000adab  pop     r14
0x18000adad  pop     rdi
0x18000adae  pop     rsi
0x18000adaf  pop     rbp
0x18000adb0  pop     rbx
0x18000adb1  retn
0x18000adb3  cmp     rsi, r8
0x18000adb6  jbe     short loc_18000AE1A
0x18000adb8  mov     eax, 2
0x18000adbd  mov     [rsp+58h+var_38], 0
0x18000adc6  mul     r8
0x18000adc9  mov     rbx, rax
0x18000adcc  test    rdx, rdx
0x18000adcf  jnz     loc_18000AEDF
0x18000add5  mov     rcx, rax
0x18000add8  sub     rcx, r8
0x18000addb  cmp     rcx, 800h
0x18000ade2  jbe     short loc_18000ADEB
0x18000ade4  lea     rbx, [r8+800h]
0x18000adeb  mov     rcx, [rdi]; pv
0x18000adee  cmp     rsi, rbx
0x18000adf1  cmova   rbx, rsi
0x18000adf5  lea     rdx, [rbx+rbx]; cb
0x18000adf9  call    cs:__imp_CoTaskMemRealloc
0x18000ae00  nop     dword ptr [rax+rax+00h]
0x18000ae05  test    rax, rax
0x18000ae08  jz      loc_18000AECB
0x18000ae0e  mov     [rdi+10h], rbx
0x18000ae12  mov     [rdi], rax
0x18000ae15  lea     rbx, [rsp+58h+Args]
0x18000ae1a  mov     rsi, [rdi+10h]
0x18000ae1e  xor     ecx, ecx
0x18000ae20  mov     r14, [rdi]
0x18000ae23  call    cs:__imp__o__set_errno
0x18000ae2a  nop     dword ptr [rax+rax+00h]
0x18000ae2f  test    rsi, rsi
0x18000ae32  jz      short loc_18000AE7E
0x18000ae34  cmp     rsi, 7FFFFFFFh
0x18000ae3b  ja      loc_18000AED2
0x18000ae41  dec     rsi
0x18000ae44  mov     r9, rbx; Args
0x18000ae47  mov     rdx, rsi; BufferCount
0x18000ae4a  mov     r8, rbp; Format
0x18000ae4d  mov     rcx, r14; Buffer
0x18000ae50  call    _vsnwprintf
0x18000ae55  test    eax, eax
0x18000ae57  js      short loc_18000AE70
0x18000ae59  cdqe
0x18000ae5b  cmp     rax, rsi
0x18000ae5e  ja      short loc_18000AE70
0x18000ae60  xor     ebx, ebx
0x18000ae62  cmp     rax, rsi
0x18000ae65  jnz     short loc_18000AE88
0x18000ae67  xor     eax, eax
0x18000ae69  mov     [r14+rsi*2], ax
0x18000ae6e  jmp     short loc_18000AE88
0x18000ae70  xor     eax, eax
0x18000ae72  mov     ebx, 8007007Ah
0x18000ae77  mov     [r14+rsi*2], ax
0x18000ae7c  jmp     short loc_18000AE88
0x18000ae7e  mov     ebx, 80070057h
0x18000ae83  test    rsi, rsi
0x18000ae86  jnz     short loc_18000AED2
0x18000ae88  cmp     ebx, 8007007Ah
0x18000ae8e  jnz     short loc_18000AEE4
0x18000ae90  lea     rcx, [rsp+58h+var_38]
0x18000ae95  mov     dword ptr [rsp+58h+var_38], 0
0x18000ae9d  call    cs:__imp__o__get_errno
0x18000aea4  nop     dword ptr [rax+rax+00h]
0x18000aea9  cmp     dword ptr [rsp+58h+var_38], 16h
0x18000aeae  jz      short loc_18000AED8
0x18000aeb0  mov     rax, [rdi+10h]
0x18000aeb4  lea     rcx, [rax+20h]
0x18000aeb8  cmp     rcx, rax
0x18000aebb  jnb     loc_18000AD1C
0x18000aec1  mov     ebx, 80070216h
0x18000aec6  jmp     loc_18000AD9D
0x18000aecb  mov     ebx, 8007000Eh
0x18000aed0  jmp     short loc_18000AEE4
0x18000aed2  xor     eax, eax
0x18000aed4  mov     [r14], ax
0x18000aed8  mov     ebx, 80070057h
0x18000aedd  jmp     short loc_18000AEE4
0x18000aedf  mov     ebx, 80070216h
0x18000aee4  test    ebx, ebx
0x18000aee6  js      loc_18000AD9D
0x18000aeec  mov     qword ptr [rdi+8], 0FFFFFFFFFFFFFFFFh
0x18000aef4  jmp     loc_18000ADA5
```
