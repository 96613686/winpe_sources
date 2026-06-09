# SxRegWriteULONGLONG(HKEY__ *,ushort const *,unsigned __int64)

- ea: `0x18001eccc`
- end: `0x18001ed98`
- name: `?SxRegWriteULONGLONG@@YAJPEAUHKEY__@@PEBG_K@Z`
- size: `204`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpValueName, unsigned __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800114b8`
- `0x180013d3c`

## callees

- `0x18001586c`
- `0x180015974`
- `0x18001eccc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001ed56`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001ed56`

## string_xrefs

- `0x18001ece9`: `SxRegWriteULONGLONG`

## pseudocode

```c
__int64 __fastcall SxRegWriteULONGLONG(HKEY hKey, LPCWSTR lpValueName, __int64 a3)
{
  __int16 v5; // ax
  signed int v6; // ebx
  LSTATUS v7; // eax
  int v9; // [rsp+30h] [rbp-40h] BYREF
  __int16 v10; // [rsp+34h] [rbp-3Ch]
  __int16 v11; // [rsp+36h] [rbp-3Ah]
  __int64 Data; // [rsp+90h] [rbp+20h] BYREF

  Data = a3;
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v9, "SxRegWriteULONGLONG", 458, 2);
  v5 = 460;
  if ( hKey && (v10 = 460, v5 = 461, lpValueName) )
  {
    v10 = 461;
    v9 = 0;
    v7 = RegSetValueExW(hKey, lpValueName, 0, 0xBu, (const BYTE *)&Data, 8u);
    v6 = v7;
    if ( v7 > 0 )
      v6 = (unsigned __int16)v7 | 0x80070000;
    v9 = v6;
    v5 = 463;
    if ( v6 >= 0 )
    {
      v10 = 463;
      goto LABEL_9;
    }
  }
  else
  {
    v6 = -2147024809;
    v9 = -2147024809;
  }
  v11 = v5;
LABEL_9:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v9);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001eccc  mov     [rsp-8+arg_0], rbx
0x18001ecd1  mov     [rsp-8+arg_8], rdi
0x18001ecd6  mov     [rsp-8+Data], r8
0x18001ecdb  push    rbp
0x18001ecdc  mov     rbp, rsp
0x18001ecdf  sub     rsp, 70h
0x18001ece3  mov     rbx, rdx
0x18001ece6  mov     rdi, rcx
0x18001ece9  lea     rdx, aSxregwriteulon; "SxRegWriteULONGLONG"
0x18001ecf0  mov     r9d, 2; unsigned __int16
0x18001ecf6  lea     rcx, [rbp+var_40]; this
0x18001ecfa  mov     r8d, 1CAh; unsigned __int16
0x18001ed00  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18001ed05  mov     eax, 1CCh
0x18001ed0a  test    rdi, rdi
0x18001ed0d  jnz     short loc_18001ED1D
0x18001ed0f  mov     ebx, 80070057h
0x18001ed14  mov     [rbp+var_40], ebx
0x18001ed17  mov     [rbp+var_3A], ax
0x18001ed1b  jmp     short loc_18001ED7B
0x18001ed1d  mov     [rbp+var_3C], ax
0x18001ed21  mov     eax, 1CDh
0x18001ed26  test    rbx, rbx
0x18001ed29  jz      short loc_18001ED0F
0x18001ed2b  mov     [rbp+var_3C], ax
0x18001ed2f  mov     r9d, 0Bh; dwType
0x18001ed35  lea     rax, [rbp+Data]
0x18001ed39  mov     [rsp+70h+cbData], 8; cbData
0x18001ed41  xor     r8d, r8d; Reserved
0x18001ed44  mov     [rsp+70h+lpData], rax; lpData
0x18001ed49  mov     rdx, rbx; lpValueName
0x18001ed4c  mov     [rbp+var_40], 0
0x18001ed53  mov     rcx, rdi; hKey
0x18001ed56  call    cs:__imp_RegSetValueExW
0x18001ed5c  mov     ebx, eax
0x18001ed5e  test    eax, eax
0x18001ed60  jle     short loc_18001ED6B
0x18001ed62  movzx   ebx, ax
0x18001ed65  or      ebx, 80070000h
0x18001ed6b  mov     [rbp+var_40], ebx
0x18001ed6e  mov     eax, 1CFh
0x18001ed73  test    ebx, ebx
0x18001ed75  js      short loc_18001ED17
0x18001ed77  mov     [rbp+var_3C], ax
0x18001ed7b  lea     rcx, [rbp+var_40]; this
0x18001ed7f  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18001ed84  lea     r11, [rsp+70h+var_s0]
0x18001ed89  mov     eax, ebx
0x18001ed8b  mov     rbx, [r11+10h]
0x18001ed8f  mov     rdi, [r11+18h]
0x18001ed93  mov     rsp, r11
0x18001ed96  pop     rbp
0x18001ed97  retn
```
