# PWSZToPSZ(ushort const *,char *,long,char * *,char * *)

- ea: `0x1800059f8`
- end: `0x180005ad4`
- name: `?PWSZToPSZ@@YAJPEBGPEADJPEAPEAD2@Z`
- size: `220`
- prototype: `__int64 __usercall@<rax>(LPCWCH lpWideCharStr@<rcx>, char *@<rdx>, int@<r8d>, char **@<r9>, char **)`
- caller_count: `10`
- callee_count: `2`
- tags: ``

## callers

- `0x18000419c`
- `0x1800042f4`
- `0x18000b95c`
- `0x18000c00c`
- `0x18000c128`
- `0x18000c798`
- `0x18000c8b8`
- `0x18000ce3c`
- `0x18000d770`
- `0x18000dcc0`

## callees

- `0x1800059f8`
- `0x1800060e4`

## import_xrefs

- `KERNEL32!WideCharToMultiByte` at `0x180005a64`
- `KERNEL32!WideCharToMultiByte` at `0x180005ab9`
- `KERNEL32!WideCharToMultiByte` at `0x180005a64`
- `KERNEL32!WideCharToMultiByte` at `0x180005ab9`

## pseudocode

```c
__int64 __fastcall PWSZToPSZ(LPCWCH lpWideCharStr, char *a2, int a3, char **a4, char **a5)
{
  CHAR *lpMultiByteStr; // rbx
  int v9; // eax
  int cbMultiByte; // r14d
  char *v11; // rax
  char *v12; // rdi

  *a4 = 0;
  lpMultiByteStr = a2;
  *a5 = 0;
  if ( lpWideCharStr )
  {
    v9 = WideCharToMultiByte(0, 0, lpWideCharStr, -1, 0, 0, 0, 0);
    cbMultiByte = v9;
    if ( v9 < a3 )
    {
      v12 = 0;
    }
    else
    {
      v11 = (char *)operator new(v9 + 1);
      v12 = v11;
      if ( !v11 )
        return 2147942414LL;
      lpMultiByteStr = v11;
    }
    WideCharToMultiByte(0, 0, lpWideCharStr, -1, lpMultiByteStr, cbMultiByte, 0, 0);
    *a4 = v12;
    *a5 = lpMultiByteStr;
  }
  else
  {
    *a2 = 0;
    *a5 = a2;
  }
  return 0;
}

```

## disassembly

```asm
0x1800059f8  push    rbx
0x1800059fa  push    rbp
0x1800059fb  push    rsi
0x1800059fc  push    rdi
0x1800059fd  push    r14
0x1800059ff  push    r15
0x180005a01  sub     rsp, 48h
0x180005a05  mov     rsi, [rsp+78h+arg_20]
0x180005a0d  mov     r15, r9
0x180005a10  mov     qword ptr [r9], 0
0x180005a17  mov     edi, r8d
0x180005a1a  mov     rbx, rdx
0x180005a1d  mov     rbp, rcx
0x180005a20  mov     qword ptr [rsi], 0
0x180005a27  test    rcx, rcx
0x180005a2a  jnz     short loc_180005A36
0x180005a2c  mov     [rdx], cl
0x180005a2e  mov     [rsi], rdx
0x180005a31  jmp     loc_180005AC5
0x180005a36  mov     [rsp+78h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x180005a3f  or      r9d, 0FFFFFFFFh; cchWideChar
0x180005a43  mov     [rsp+78h+lpDefaultChar], 0; lpDefaultChar
0x180005a4c  mov     r8, rbp; lpWideCharStr
0x180005a4f  mov     [rsp+78h+cbMultiByte], 0; cbMultiByte
0x180005a57  xor     edx, edx; dwFlags
0x180005a59  xor     ecx, ecx; CodePage
0x180005a5b  mov     [rsp+78h+lpMultiByteStr], 0; lpMultiByteStr
0x180005a64  call    cs:__imp_WideCharToMultiByte
0x180005a6a  mov     r14d, eax
0x180005a6d  cmp     eax, edi
0x180005a6f  jl      short loc_180005A90
0x180005a71  lea     ecx, [rax+1]
0x180005a74  movsxd  rcx, ecx; Size
0x180005a77  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005a7c  mov     rdi, rax
0x180005a7f  test    rax, rax
0x180005a82  jnz     short loc_180005A8B
0x180005a84  mov     eax, 8007000Eh
0x180005a89  jmp     short loc_180005AC7
0x180005a8b  mov     rbx, rax
0x180005a8e  jmp     short loc_180005A92
0x180005a90  xor     edi, edi
0x180005a92  mov     [rsp+78h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x180005a9b  or      r9d, 0FFFFFFFFh; cchWideChar
0x180005a9f  mov     [rsp+78h+lpDefaultChar], 0; lpDefaultChar
0x180005aa8  mov     r8, rbp; lpWideCharStr
0x180005aab  mov     [rsp+78h+cbMultiByte], r14d; cbMultiByte
0x180005ab0  xor     edx, edx; dwFlags
0x180005ab2  xor     ecx, ecx; CodePage
0x180005ab4  mov     [rsp+78h+lpMultiByteStr], rbx; lpMultiByteStr
0x180005ab9  call    cs:__imp_WideCharToMultiByte
0x180005abf  mov     [r15], rdi
0x180005ac2  mov     [rsi], rbx
0x180005ac5  xor     eax, eax
0x180005ac7  add     rsp, 48h
0x180005acb  pop     r15
0x180005acd  pop     r14
0x180005acf  pop     rdi
0x180005ad0  pop     rsi
0x180005ad1  pop     rbp
0x180005ad2  pop     rbx
0x180005ad3  retn
```
