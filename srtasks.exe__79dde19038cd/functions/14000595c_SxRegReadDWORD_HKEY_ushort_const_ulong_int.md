# SxRegReadDWORD(HKEY__ *,ushort const *,ulong *,int)

- ea: `0x14000595c`
- end: `0x140005aba`
- name: `?SxRegReadDWORD@@YAJPEAUHKEY__@@PEBGPEAKH@Z`
- size: `350`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpValueName, unsigned int *, int)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x1400022c0`
- `0x1400039e4`
- `0x140004410`
- `0x140005784`
- `0x140006ab0`

## callees

- `0x14000595c`
- `0x14000e324`
- `0x14000e41c`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x140005a11`
- `ADVAPI32!RegQueryValueExW` at `0x140005a11`

## string_xrefs

- `0x140005983`: `SxRegReadDWORD`

## pseudocode

```c
__int64 __fastcall SxRegReadDWORD(HKEY hKey, LPCWSTR lpValueName, unsigned int *a3, int a4)
{
  __int64 v8; // rdx
  __int64 v9; // r8
  __int16 v10; // ax
  unsigned int v11; // ebx
  int v12; // eax
  __int16 v13; // ax
  BYTE Data[8]; // [rsp+30h] [rbp-40h] BYREF
  int v16; // [rsp+38h] [rbp-38h] BYREF
  __int16 v17; // [rsp+3Ch] [rbp-34h]
  __int16 v18; // [rsp+3Eh] [rbp-32h]
  int v19; // [rsp+40h] [rbp-30h]
  DWORD cbData; // [rsp+98h] [rbp+28h] BYREF
  DWORD Type; // [rsp+A0h] [rbp+30h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v16, "SxRegReadDWORD", 33, 2);
  *(_DWORD *)Data = 0;
  Type = 0;
  cbData = 0;
  if ( a3 )
    *a3 = 0;
  v10 = 42;
  if ( lpValueName && (v17 = 42, v10 = 43, a3) )
  {
    v17 = 43;
    v16 = 0;
    cbData = 4;
    v12 = RegQueryValueExW(hKey, lpValueName, 0, &Type, Data, &cbData);
    if ( a4 && v12 == 2 )
    {
      v11 = 1;
      v16 = 1;
      v13 = 49;
LABEL_19:
      v17 = v13;
      goto LABEL_20;
    }
    if ( v12 > 0 )
      v12 = (unsigned __int16)v12 | 0x80070000;
    v16 = v12;
    if ( v12 < 0 )
    {
      v18 = 52;
      v19 = 1;
      v11 = v12;
      goto LABEL_20;
    }
    v10 = 54;
    v17 = 52;
    if ( Type == 4 )
    {
      v17 = 54;
      if ( cbData == 4 )
      {
        *a3 = *(_DWORD *)Data;
        v13 = 59;
        v11 = 0;
        v16 = 0;
        goto LABEL_19;
      }
      v11 = -2147467259;
      v10 = 55;
    }
    else
    {
      v11 = -2147023267;
    }
  }
  else
  {
    v11 = -2147024809;
  }
  v16 = v11;
  v18 = v10;
LABEL_20:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v16, v8, v9);
  return v11;
}

```

## disassembly

```asm
0x14000595c  mov     [rsp-18h+arg_0], rbx
0x140005961  mov     [rsp-18h+arg_18], rsi
0x140005966  push    rbp
0x140005967  push    rdi
0x140005968  push    r14
0x14000596a  mov     rbp, rsp
0x14000596d  sub     rsp, 70h
0x140005971  mov     esi, r9d
0x140005974  mov     rbx, r8
0x140005977  mov     r9d, 2; unsigned __int16
0x14000597d  mov     rdi, rdx
0x140005980  mov     r14, rcx
0x140005983  lea     rdx, aSxregreaddword; "SxRegReadDWORD"
0x14000598a  lea     rcx, [rbp+var_38]; this
0x14000598e  lea     r8d, [r9+1Fh]; unsigned __int16
0x140005992  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x140005997  mov     dword ptr [rbp+Data], 0
0x14000599e  mov     [rbp+Type], 0
0x1400059a5  mov     [rbp+cbData], 0
0x1400059ac  test    rbx, rbx
0x1400059af  jz      short loc_1400059B7
0x1400059b1  mov     dword ptr [rbx], 0
0x1400059b7  mov     eax, 2Ah ; '*'
0x1400059bc  test    rdi, rdi
0x1400059bf  jnz     short loc_1400059D2
0x1400059c1  mov     ebx, 80070057h
0x1400059c6  mov     [rbp+var_38], ebx
0x1400059c9  mov     [rbp+var_32], ax
0x1400059cd  jmp     loc_140005A9A
0x1400059d2  mov     [rbp+var_34], ax
0x1400059d6  mov     eax, 2Bh ; '+'
0x1400059db  test    rbx, rbx
0x1400059de  jz      short loc_1400059C1
0x1400059e0  mov     [rbp+var_34], ax
0x1400059e4  lea     r9, [rbp+Type]; lpType
0x1400059e8  lea     rax, [rbp+cbData]
0x1400059ec  mov     [rbp+var_38], 0
0x1400059f3  mov     [rsp+70h+lpcbData], rax; lpcbData
0x1400059f8  xor     r8d, r8d; lpReserved
0x1400059fb  lea     rax, [rbp+Data]
0x1400059ff  mov     [rbp+cbData], 4
0x140005a06  mov     rdx, rdi; lpValueName
0x140005a09  mov     [rsp+70h+lpData], rax; lpData
0x140005a0e  mov     rcx, r14; hKey
0x140005a11  call    cs:__imp_RegQueryValueExW
0x140005a17  test    esi, esi
0x140005a19  jz      short loc_140005A2B
0x140005a1b  cmp     eax, 2
0x140005a1e  jnz     short loc_140005A2B
0x140005a20  lea     ebx, [rax-1]
0x140005a23  mov     [rbp+var_38], ebx
0x140005a26  lea     eax, [rbx+30h]
0x140005a29  jmp     short loc_140005A96
0x140005a2b  test    eax, eax
0x140005a2d  jle     short loc_140005A37
0x140005a2f  movzx   eax, ax
0x140005a32  or      eax, 80070000h
0x140005a37  mov     [rbp+var_38], eax
0x140005a3a  mov     ecx, 34h ; '4'
0x140005a3f  test    eax, eax
0x140005a41  jns     short loc_140005A51
0x140005a43  lea     ebx, [rcx-33h]
0x140005a46  mov     [rbp+var_32], cx
0x140005a4a  mov     [rbp+var_30], ebx
0x140005a4d  mov     ebx, eax
0x140005a4f  jmp     short loc_140005A9A
0x140005a51  cmp     [rbp+Type], 4
0x140005a55  mov     eax, 36h ; '6'
0x140005a5a  mov     [rbp+var_34], cx
0x140005a5e  jz      short loc_140005A6A
0x140005a60  mov     ebx, 8007065Dh
0x140005a65  jmp     loc_1400059C6
0x140005a6a  cmp     [rbp+cbData], 4
0x140005a6e  mov     [rbp+var_34], ax
0x140005a72  jz      short loc_140005A83
0x140005a74  mov     ebx, 80004005h
0x140005a79  mov     eax, 37h ; '7'
0x140005a7e  jmp     loc_1400059C6
0x140005a83  mov     eax, dword ptr [rbp+Data]
0x140005a86  mov     [rbx], eax
0x140005a88  mov     eax, 3Bh ; ';'
0x140005a8d  xor     ebx, ebx
0x140005a8f  mov     [rbp+var_38], 0
0x140005a96  mov     [rbp+var_34], ax
0x140005a9a  lea     rcx, [rbp+var_38]; this
0x140005a9e  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x140005aa3  lea     r11, [rsp+70h+var_s0]
0x140005aa8  mov     eax, ebx
0x140005aaa  mov     rbx, [r11+20h]
0x140005aae  mov     rsi, [r11+38h]
0x140005ab2  mov     rsp, r11
0x140005ab5  pop     r14
0x140005ab7  pop     rdi
0x140005ab8  pop     rbp
0x140005ab9  retn
```
