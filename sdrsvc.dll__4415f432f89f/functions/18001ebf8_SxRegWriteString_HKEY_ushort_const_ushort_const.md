# SxRegWriteString(HKEY__ *,ushort const *,ushort const *)

- ea: `0x18001ebf8`
- end: `0x18001ecc4`
- name: `?SxRegWriteString@@YAJPEAUHKEY__@@PEBG1@Z`
- size: `204`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpValueName, BYTE *lpData)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180013d3c`

## callees

- `0x18001586c`
- `0x180015974`
- `0x18001ebf8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001ec89`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001ec89`

## string_xrefs

- `0x18001ec0f`: `SxRegWriteString`

## pseudocode

```c
__int64 __fastcall SxRegWriteString(HKEY hKey, LPCWSTR lpValueName, BYTE *lpData)
{
  __int16 v6; // ax
  signed int v7; // ebx
  __int64 v8; // rax
  LSTATUS v9; // eax
  int v11; // [rsp+30h] [rbp-40h] BYREF
  __int16 v12; // [rsp+34h] [rbp-3Ch]
  __int16 v13; // [rsp+36h] [rbp-3Ah]

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v11, "SxRegWriteString", 478, 2);
  v6 = 480;
  if ( hKey && (v12 = 480, v6 = 481, lpData) )
  {
    v12 = 481;
    v8 = -1;
    v11 = 0;
    do
      ++v8;
    while ( *(_WORD *)&lpData[2 * v8] );
    v9 = RegSetValueExW(hKey, lpValueName, 0, 1u, lpData, 2 * v8 + 2);
    v7 = v9;
    if ( v9 > 0 )
      v7 = (unsigned __int16)v9 | 0x80070000;
    v11 = v7;
    v6 = 483;
    if ( v7 >= 0 )
    {
      v12 = 483;
      goto LABEL_11;
    }
  }
  else
  {
    v7 = -2147024809;
    v11 = -2147024809;
  }
  v13 = v6;
LABEL_11:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v11);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001ebf8  push    rbp
0x18001ebfa  push    rbx
0x18001ebfb  push    rsi
0x18001ebfc  push    rdi
0x18001ebfd  push    r14
0x18001ebff  mov     rbp, rsp
0x18001ec02  sub     rsp, 70h
0x18001ec06  mov     rbx, r8
0x18001ec09  mov     rsi, rdx
0x18001ec0c  mov     rdi, rcx
0x18001ec0f  lea     rdx, aSxregwritestri; "SxRegWriteString"
0x18001ec16  mov     r8d, 1DEh; unsigned __int16
0x18001ec1c  lea     rcx, [rbp+var_40]; this
0x18001ec20  mov     r9d, 2; unsigned __int16
0x18001ec26  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18001ec2b  xor     r14d, r14d
0x18001ec2e  mov     eax, 1E0h
0x18001ec33  test    rdi, rdi
0x18001ec36  jnz     short loc_18001EC46
0x18001ec38  mov     ebx, 80070057h
0x18001ec3d  mov     [rbp+var_40], ebx
0x18001ec40  mov     [rbp+var_3A], ax
0x18001ec44  jmp     short loc_18001ECAE
0x18001ec46  mov     [rbp+var_3C], ax
0x18001ec4a  mov     eax, 1E1h
0x18001ec4f  test    rbx, rbx
0x18001ec52  jz      short loc_18001EC38
0x18001ec54  mov     [rbp+var_3C], ax
0x18001ec58  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001ec5c  mov     [rbp+var_40], r14d
0x18001ec60  inc     rax
0x18001ec63  cmp     [rbx+rax*2], r14w
0x18001ec68  jnz     short loc_18001EC60
0x18001ec6a  lea     eax, ds:2[rax*2]
0x18001ec71  mov     r9d, 1; dwType
0x18001ec77  mov     [rsp+70h+cbData], eax; cbData
0x18001ec7b  xor     r8d, r8d; Reserved
0x18001ec7e  mov     rdx, rsi; lpValueName
0x18001ec81  mov     [rsp+70h+lpData], rbx; lpData
0x18001ec86  mov     rcx, rdi; hKey
0x18001ec89  call    cs:__imp_RegSetValueExW
0x18001ec8f  mov     ebx, eax
0x18001ec91  test    eax, eax
0x18001ec93  jle     short loc_18001EC9E
0x18001ec95  movzx   ebx, ax
0x18001ec98  or      ebx, 80070000h
0x18001ec9e  mov     [rbp+var_40], ebx
0x18001eca1  mov     eax, 1E3h
0x18001eca6  test    ebx, ebx
0x18001eca8  js      short loc_18001EC40
0x18001ecaa  mov     [rbp+var_3C], ax
0x18001ecae  lea     rcx, [rbp+var_40]; this
0x18001ecb2  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18001ecb7  mov     eax, ebx
0x18001ecb9  add     rsp, 70h
0x18001ecbd  pop     r14
0x18001ecbf  pop     rdi
0x18001ecc0  pop     rsi
0x18001ecc1  pop     rbx
0x18001ecc2  pop     rbp
0x18001ecc3  retn
```
