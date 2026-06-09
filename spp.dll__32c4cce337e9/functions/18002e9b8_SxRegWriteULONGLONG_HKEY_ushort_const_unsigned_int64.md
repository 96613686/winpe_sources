# SxRegWriteULONGLONG(HKEY__ *,ushort const *,unsigned __int64)

- ea: `0x18002e9b8`
- end: `0x18002ea84`
- name: `?SxRegWriteULONGLONG@@YAJPEAUHKEY__@@PEBG_K@Z`
- size: `204`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpValueName, unsigned __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000a430`
- `0x18000e7b0`

## callees

- `0x1800268b4`
- `0x1800269ac`
- `0x18002e9b8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002ea42`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002ea42`

## string_xrefs

- `0x18002e9d5`: `SxRegWriteULONGLONG`

## pseudocode

```c
__int64 __fastcall SxRegWriteULONGLONG(HKEY hKey, LPCWSTR lpValueName, __int64 a3)
{
  __int64 v5; // rdx
  __int64 v6; // r8
  __int16 v7; // ax
  signed int v8; // ebx
  LSTATUS v9; // eax
  int v11; // [rsp+30h] [rbp-40h] BYREF
  __int16 v12; // [rsp+34h] [rbp-3Ch]
  __int16 v13; // [rsp+36h] [rbp-3Ah]
  __int64 Data; // [rsp+90h] [rbp+20h] BYREF

  Data = a3;
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v11, "SxRegWriteULONGLONG", 458, 2);
  v7 = 460;
  if ( hKey && (v12 = 460, v7 = 461, lpValueName) )
  {
    v12 = 461;
    v11 = 0;
    v9 = RegSetValueExW(hKey, lpValueName, 0, 0xBu, (const BYTE *)&Data, 8u);
    v8 = v9;
    if ( v9 > 0 )
      v8 = (unsigned __int16)v9 | 0x80070000;
    v11 = v8;
    v7 = 463;
    if ( v8 >= 0 )
    {
      v12 = 463;
      goto LABEL_9;
    }
  }
  else
  {
    v8 = -2147024809;
    v11 = -2147024809;
  }
  v13 = v7;
LABEL_9:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v11, v5, v6);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18002e9b8  mov     [rsp-8+arg_0], rbx
0x18002e9bd  mov     [rsp-8+arg_8], rdi
0x18002e9c2  mov     [rsp-8+Data], r8
0x18002e9c7  push    rbp
0x18002e9c8  mov     rbp, rsp
0x18002e9cb  sub     rsp, 70h
0x18002e9cf  mov     rbx, rdx
0x18002e9d2  mov     rdi, rcx
0x18002e9d5  lea     rdx, aSxregwriteulon; "SxRegWriteULONGLONG"
0x18002e9dc  mov     r9d, 2; unsigned __int16
0x18002e9e2  lea     rcx, [rbp+var_40]; this
0x18002e9e6  mov     r8d, 1CAh; unsigned __int16
0x18002e9ec  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18002e9f1  mov     eax, 1CCh
0x18002e9f6  test    rdi, rdi
0x18002e9f9  jnz     short loc_18002EA09
0x18002e9fb  mov     ebx, 80070057h
0x18002ea00  mov     [rbp+var_40], ebx
0x18002ea03  mov     [rbp+var_3A], ax
0x18002ea07  jmp     short loc_18002EA67
0x18002ea09  mov     [rbp+var_3C], ax
0x18002ea0d  mov     eax, 1CDh
0x18002ea12  test    rbx, rbx
0x18002ea15  jz      short loc_18002E9FB
0x18002ea17  mov     [rbp+var_3C], ax
0x18002ea1b  mov     r9d, 0Bh; dwType
0x18002ea21  lea     rax, [rbp+Data]
0x18002ea25  mov     [rsp+70h+cbData], 8; cbData
0x18002ea2d  xor     r8d, r8d; Reserved
0x18002ea30  mov     [rsp+70h+lpData], rax; lpData
0x18002ea35  mov     rdx, rbx; lpValueName
0x18002ea38  mov     [rbp+var_40], 0
0x18002ea3f  mov     rcx, rdi; hKey
0x18002ea42  call    cs:__imp_RegSetValueExW
0x18002ea48  mov     ebx, eax
0x18002ea4a  test    eax, eax
0x18002ea4c  jle     short loc_18002EA57
0x18002ea4e  movzx   ebx, ax
0x18002ea51  or      ebx, 80070000h
0x18002ea57  mov     [rbp+var_40], ebx
0x18002ea5a  mov     eax, 1CFh
0x18002ea5f  test    ebx, ebx
0x18002ea61  js      short loc_18002EA03
0x18002ea63  mov     [rbp+var_3C], ax
0x18002ea67  lea     rcx, [rbp+var_40]; this
0x18002ea6b  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18002ea70  lea     r11, [rsp+70h+var_s0]
0x18002ea75  mov     eax, ebx
0x18002ea77  mov     rbx, [r11+10h]
0x18002ea7b  mov     rdi, [r11+18h]
0x18002ea7f  mov     rsp, r11
0x18002ea82  pop     rbp
0x18002ea83  retn
```
