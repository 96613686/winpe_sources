# SxRegWriteDWORD(HKEY__ *,ushort const *,ulong)

- ea: `0x18001eb28`
- end: `0x18001ebf1`
- name: `?SxRegWriteDWORD@@YAJPEAUHKEY__@@PEBGK@Z`
- size: `201`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpValueName, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180012948`
- `0x180013d3c`

## callees

- `0x18001586c`
- `0x180015974`
- `0x18001eb28`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001ebaf`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001ebaf`

## string_xrefs

- `0x18001eb45`: `SxRegWriteDWORD`

## pseudocode

```c
__int64 __fastcall SxRegWriteDWORD(HKEY hKey, LPCWSTR lpValueName, int a3)
{
  __int16 v5; // ax
  signed int v6; // ebx
  LSTATUS v7; // eax
  int v9; // [rsp+30h] [rbp-40h] BYREF
  __int16 v10; // [rsp+34h] [rbp-3Ch]
  __int16 v11; // [rsp+36h] [rbp-3Ah]
  int Data; // [rsp+90h] [rbp+20h] BYREF

  Data = a3;
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v9, "SxRegWriteDWORD", 438, 2);
  v5 = 440;
  if ( hKey && (v10 = 440, v5 = 441, lpValueName) )
  {
    v10 = 441;
    v9 = 0;
    v7 = RegSetValueExW(hKey, lpValueName, 0, 4u, (const BYTE *)&Data, 4u);
    v6 = v7;
    if ( v7 > 0 )
      v6 = (unsigned __int16)v7 | 0x80070000;
    v9 = v6;
    v5 = 443;
    if ( v6 >= 0 )
    {
      v10 = 443;
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
0x18001eb28  mov     [rsp-8+arg_0], rbx
0x18001eb2d  mov     [rsp-8+arg_8], rdi
0x18001eb32  mov     [rsp-8+Data], r8d
0x18001eb37  push    rbp
0x18001eb38  mov     rbp, rsp
0x18001eb3b  sub     rsp, 70h
0x18001eb3f  mov     rbx, rdx
0x18001eb42  mov     rdi, rcx
0x18001eb45  lea     rdx, aSxregwritedwor; "SxRegWriteDWORD"
0x18001eb4c  mov     r9d, 2; unsigned __int16
0x18001eb52  lea     rcx, [rbp+var_40]; this
0x18001eb56  mov     r8d, 1B6h; unsigned __int16
0x18001eb5c  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18001eb61  mov     eax, 1B8h
0x18001eb66  test    rdi, rdi
0x18001eb69  jnz     short loc_18001EB79
0x18001eb6b  mov     ebx, 80070057h
0x18001eb70  mov     [rbp+var_40], ebx
0x18001eb73  mov     [rbp+var_3A], ax
0x18001eb77  jmp     short loc_18001EBD4
0x18001eb79  mov     [rbp+var_3C], ax
0x18001eb7d  mov     eax, 1B9h
0x18001eb82  test    rbx, rbx
0x18001eb85  jz      short loc_18001EB6B
0x18001eb87  mov     [rbp+var_3C], ax
0x18001eb8b  mov     r9d, 4; dwType
0x18001eb91  lea     rax, [rbp+Data]
0x18001eb95  mov     [rsp+70h+cbData], r9d; cbData
0x18001eb9a  xor     r8d, r8d; Reserved
0x18001eb9d  mov     [rsp+70h+lpData], rax; lpData
0x18001eba2  mov     rdx, rbx; lpValueName
0x18001eba5  mov     [rbp+var_40], 0
0x18001ebac  mov     rcx, rdi; hKey
0x18001ebaf  call    cs:__imp_RegSetValueExW
0x18001ebb5  mov     ebx, eax
0x18001ebb7  test    eax, eax
0x18001ebb9  jle     short loc_18001EBC4
0x18001ebbb  movzx   ebx, ax
0x18001ebbe  or      ebx, 80070000h
0x18001ebc4  mov     [rbp+var_40], ebx
0x18001ebc7  mov     eax, 1BBh
0x18001ebcc  test    ebx, ebx
0x18001ebce  js      short loc_18001EB73
0x18001ebd0  mov     [rbp+var_3C], ax
0x18001ebd4  lea     rcx, [rbp+var_40]; this
0x18001ebd8  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18001ebdd  lea     r11, [rsp+70h+var_s0]
0x18001ebe2  mov     eax, ebx
0x18001ebe4  mov     rbx, [r11+10h]
0x18001ebe8  mov     rdi, [r11+18h]
0x18001ebec  mov     rsp, r11
0x18001ebef  pop     rbp
0x18001ebf0  retn
```
