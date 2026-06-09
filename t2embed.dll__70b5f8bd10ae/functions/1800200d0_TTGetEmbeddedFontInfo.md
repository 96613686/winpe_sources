# TTGetEmbeddedFontInfo

- ea: `0x1800200d0`
- end: `0x1800201ba`
- name: `TTGetEmbeddedFontInfo`
- size: `234`
- prototype: `LONG __stdcall(ULONG ulFlags, ULONG *pulPrivStatus, ULONG ulPrivs, ULONG *pulStatus, READEMBEDPROC lpfnReadFromStream, LPVOID lpvReadStream, TTLOADINFO *pTTLoadInfo)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1800200d0`
- `0x18002173c`
- `0x18002a566`
- `0x18002a590`

## pseudocode

```c
LONG __stdcall TTGetEmbeddedFontInfo(
        ULONG ulFlags,
        ULONG *pulPrivStatus,
        ULONG ulPrivs,
        ULONG *pulStatus,
        READEMBEDPROC lpfnReadFromStream,
        LPVOID lpvReadStream,
        TTLOADINFO *pTTLoadInfo)
{
  int v7; // r15d
  int v9; // r14d
  ULONG v10; // edi
  LONG EmbeddedFontInfo; // ecx
  LONG result; // eax
  _BYTE v13[944]; // [rsp+50h] [rbp-3F8h] BYREF
  LONG v14; // [rsp+400h] [rbp-48h]

  v7 = (int)pulStatus;
  v9 = (int)pulPrivStatus;
  v10 = ulFlags | 1;
  memset_0(v13, 0, 0x3B8u);
  v14 = 0;
  EmbeddedFontInfo = T2GetEmbeddedFontInfo(
                       v10,
                       v9,
                       ulPrivs,
                       v7,
                       (__int64)lpfnReadFromStream,
                       (__int64)lpvReadStream,
                       (__int64)pTTLoadInfo,
                       (__int64)v13);
  if ( !EmbeddedFontInfo )
    return 0;
  result = v14;
  if ( !v14 )
    return EmbeddedFontInfo;
  return result;
}

```

## disassembly

```asm
0x1800200d0  mov     [rsp+arg_0], rbx
0x1800200d5  mov     [rsp+arg_10], rsi
0x1800200da  push    rdi
0x1800200db  push    r12
0x1800200dd  push    r13
0x1800200df  push    r14
0x1800200e1  push    r15
0x1800200e3  sub     rsp, 420h
0x1800200ea  mov     rax, cs:__security_cookie
0x1800200f1  xor     rax, rsp
0x1800200f4  mov     [rsp+448h+var_38], rax
0x1800200fc  mov     r15, r9
0x1800200ff  mov     esi, r8d
0x180020102  mov     r14, rdx
0x180020105  mov     edi, ecx
0x180020107  mov     r12, [rsp+448h+lpfnReadFromStream]
0x18002010f  mov     r13, [rsp+448h+lpvReadStream]
0x180020117  mov     rax, [rsp+448h+pTTLoadInfo]
0x18002011f  mov     [rsp+448h+var_408], rax
0x180020124  xor     ebx, ebx
0x180020126  or      edi, 1
0x180020129  xor     edx, edx; Val
0x18002012b  mov     r8d, 3B8h; Size
0x180020131  lea     rcx, [rsp+448h+var_3F8]; void *
0x180020136  call    memset_0
0x18002013b  mov     [rsp+448h+var_48], ebx
0x180020142  lea     rax, [rsp+448h+var_3F8]
0x180020147  mov     [rsp+448h+var_410], rax
0x18002014c  mov     rax, [rsp+448h+var_408]
0x180020151  mov     [rsp+448h+var_418], rax
0x180020156  mov     [rsp+448h+var_420], r13
0x18002015b  mov     [rsp+448h+var_428], r12
0x180020160  mov     r9, r15
0x180020163  mov     r8d, esi
0x180020166  mov     rdx, r14
0x180020169  mov     ecx, edi
0x18002016b  call    T2GetEmbeddedFontInfo
0x180020170  mov     ecx, eax
0x180020172  test    eax, eax
0x180020174  jz      short loc_180020184
0x180020176  mov     eax, [rsp+448h+var_48]
0x18002017d  test    eax, eax
0x18002017f  cmovz   eax, ecx
0x180020182  jmp     short loc_18002018D
0x180020184  jmp     short loc_18002018B
0x180020186  mov     ebx, 13h
0x18002018b  mov     eax, ebx
0x18002018d  mov     rcx, [rsp+448h+var_38]
0x180020195  xor     rcx, rsp; StackCookie
0x180020198  call    __security_check_cookie
0x18002019d  lea     r11, [rsp+448h+var_28]
0x1800201a5  mov     rbx, [r11+30h]
0x1800201a9  mov     rsi, [r11+40h]
0x1800201ad  mov     rsp, r11
0x1800201b0  pop     r15
0x1800201b2  pop     r14
0x1800201b4  pop     r13
0x1800201b6  pop     r12
0x1800201b8  pop     rdi
0x1800201b9  retn
```
