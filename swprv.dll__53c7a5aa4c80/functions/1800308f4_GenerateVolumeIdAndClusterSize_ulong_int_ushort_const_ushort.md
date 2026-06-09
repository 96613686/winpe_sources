# GenerateVolumeIdAndClusterSize(ulong,int,ushort const *,ushort *)

- ea: `0x1800308f4`
- end: `0x180030a90`
- name: `?GenerateVolumeIdAndClusterSize@@YAJKHPEBGPEAG@Z`
- size: `412`
- prototype: `__int64 __fastcall(int, int, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180030e48`

## callees

- `0x180001580`
- `0x18000212c`
- `0x180007650`
- `0x1800308f4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180030a05`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180030a05`

## pseudocode

```c
__int64 __fastcall GenerateVolumeIdAndClusterSize(int a1, int a2, const unsigned __int16 *a3, unsigned __int16 *a4)
{
  size_t *v8; // r8
  __int16 v9; // bx
  HRESULT v10; // r11d
  unsigned __int16 v11; // cx
  GUID pclsid; // [rsp+30h] [rbp-39h] BYREF
  wchar_t pszDest; // [rsp+40h] [rbp-29h] BYREF
  _BYTE v15[78]; // [rsp+42h] [rbp-27h] BYREF

  pszDest = 0;
  memset_0(v15, 0, 0x4Cu);
  pclsid = GUID_NULL;
  if ( a3 && a4 )
  {
    *a4 = 0;
    switch ( a1 )
    {
      case 0x200:
        v9 = 1;
        break;
      case 0x400:
        v9 = 2;
        break;
      case 0x800:
        v9 = 3;
        break;
      case 0x1000:
        v9 = 4;
        break;
      case 0x2000:
        v9 = 5;
        break;
      case 0x4000:
        v9 = 6;
        break;
      case 0x8000:
        v9 = 7;
        break;
      default:
        v9 = 0;
        if ( a1 == 0x10000 )
          v9 = 8;
        break;
    }
    v10 = StringCopyWorkerW(&pszDest, 0x27u, v8, a3 + 10, 0x26u);
    if ( v10 >= 0 )
    {
      v10 = CLSIDFromString(&pszDest, &pclsid);
      if ( v10 >= 0 )
      {
        v11 = *(_WORD *)&pclsid.Data4[6]
            ^ *(_WORD *)&pclsid.Data4[4]
            ^ *(_WORD *)&pclsid.Data4[2]
            ^ *(_WORD *)pclsid.Data4
            ^ pclsid.Data3
            ^ pclsid.Data2
            ^ HIWORD(pclsid.Data1)
            ^ LOWORD(pclsid.Data1);
        *a4 = (a2 != 0) | ((v9 << 12) | (v11 ^ (v11 >> 4)) & 0xFFF) ^ 1;
      }
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800308f4  mov     [rsp-8+arg_0], rbx
0x1800308f9  mov     [rsp-8+arg_8], rsi
0x1800308fe  push    rbp
0x1800308ff  push    rdi
0x180030900  push    r12
0x180030902  push    r14
0x180030904  push    r15
0x180030906  lea     rbp, [rsp-37h]
0x18003090b  sub     rsp, 0A0h
0x180030912  mov     rax, cs:__security_cookie
0x180030919  xor     rax, rsp
0x18003091c  mov     [rbp+57h+var_30], rax
0x180030920  xor     eax, eax
0x180030922  mov     r14, r8
0x180030925  mov     r15d, edx
0x180030928  mov     [rbp+57h+pszDest], ax
0x18003092c  mov     edi, ecx
0x18003092e  xor     edx, edx; Val
0x180030930  lea     rcx, [rbp+57h+var_7E]; void *
0x180030934  mov     rsi, r9
0x180030937  lea     r8d, [rax+4Ch]; Size
0x18003093b  call    memset_0
0x180030940  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180030947  movdqu  xmmword ptr [rbp+57h+pclsid.Data1], xmm0
0x18003094c  test    r14, r14
0x18003094f  jz      loc_180030A5F
0x180030955  test    rsi, rsi
0x180030958  jz      loc_180030A5F
0x18003095e  xor     eax, eax
0x180030960  mov     [rsi], ax
0x180030963  lea     r12d, [rax+1]
0x180030967  cmp     edi, 200h
0x18003096d  jz      short loc_1800309D8
0x18003096f  cmp     edi, 400h
0x180030975  jz      short loc_1800309D1
0x180030977  cmp     edi, 800h
0x18003097d  jz      short loc_1800309CA
0x18003097f  cmp     edi, 1000h
0x180030985  jz      short loc_1800309C3
0x180030987  cmp     edi, 2000h
0x18003098d  jz      short loc_1800309BC
0x18003098f  cmp     edi, 4000h
0x180030995  jz      short loc_1800309B5
0x180030997  cmp     edi, 8000h
0x18003099d  jz      short loc_1800309AE
0x18003099f  xor     ebx, ebx
0x1800309a1  cmp     edi, 10000h
0x1800309a7  jnz     short loc_1800309DB
0x1800309a9  lea     ebx, [rax+8]
0x1800309ac  jmp     short loc_1800309DB
0x1800309ae  mov     ebx, 7
0x1800309b3  jmp     short loc_1800309DB
0x1800309b5  mov     ebx, 6
0x1800309ba  jmp     short loc_1800309DB
0x1800309bc  mov     ebx, 5
0x1800309c1  jmp     short loc_1800309DB
0x1800309c3  mov     ebx, 4
0x1800309c8  jmp     short loc_1800309DB
0x1800309ca  mov     ebx, 3
0x1800309cf  jmp     short loc_1800309DB
0x1800309d1  mov     ebx, 2
0x1800309d6  jmp     short loc_1800309DB
0x1800309d8  mov     ebx, r12d
0x1800309db  lea     r9, [r14+14h]; pszSrc
0x1800309df  mov     [rsp+0C0h+cchToCopy], 26h ; '&'; cchToCopy
0x1800309e8  mov     edx, 27h ; '''; cchDest
0x1800309ed  lea     rcx, [rbp+57h+pszDest]; pszDest
0x1800309f1  call    StringCopyWorkerW
0x1800309f6  mov     r11d, eax
0x1800309f9  test    eax, eax
0x1800309fb  js      short loc_180030A65
0x1800309fd  lea     rdx, [rbp+57h+pclsid]; pclsid
0x180030a01  lea     rcx, [rbp+57h+pszDest]; lpsz
0x180030a05  call    cs:__imp_CLSIDFromString
0x180030a0b  mov     r11d, eax
0x180030a0e  test    eax, eax
0x180030a10  js      short loc_180030A65
0x180030a12  movzx   ecx, word ptr [rbp+57h+pclsid.Data1]
0x180030a16  mov     eax, 0FFFh
0x180030a1b  xor     cx, word ptr [rbp+57h+pclsid.Data1+2]
0x180030a1f  xor     cx, [rbp+57h+pclsid.Data2]
0x180030a23  xor     cx, [rbp+57h+pclsid.Data3]
0x180030a27  xor     cx, word ptr [rbp+57h+pclsid.Data4]
0x180030a2b  xor     cx, word ptr [rbp+57h+pclsid.Data4+2]
0x180030a2f  xor     cx, word ptr [rbp+57h+pclsid.Data4+4]
0x180030a33  xor     cx, word ptr [rbp+57h+pclsid.Data4+6]
0x180030a37  shl     bx, 0Ch
0x180030a3b  movzx   edx, cx
0x180030a3e  shr     dx, 4
0x180030a42  xor     dx, cx
0x180030a45  and     dx, ax
0x180030a48  xor     eax, eax
0x180030a4a  or      dx, bx
0x180030a4d  xor     dx, r12w
0x180030a51  test    r15d, r15d
0x180030a54  setnz   al
0x180030a57  or      dx, ax
0x180030a5a  mov     [rsi], dx
0x180030a5d  jmp     short loc_180030A65
0x180030a5f  mov     r11d, 80070057h
0x180030a65  mov     eax, r11d
0x180030a68  mov     rcx, [rbp+57h+var_30]
0x180030a6c  xor     rcx, rsp; StackCookie
0x180030a6f  call    __security_check_cookie
0x180030a74  lea     r11, [rsp+0C0h+var_20]
0x180030a7c  mov     rbx, [r11+30h]
0x180030a80  mov     rsi, [r11+38h]
0x180030a84  mov     rsp, r11
0x180030a87  pop     r15
0x180030a89  pop     r14
0x180030a8b  pop     r12
0x180030a8d  pop     rdi
0x180030a8e  pop     rbp
0x180030a8f  retn
```
