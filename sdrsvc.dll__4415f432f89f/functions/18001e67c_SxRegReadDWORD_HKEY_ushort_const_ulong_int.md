# SxRegReadDWORD(HKEY__ *,ushort const *,ulong *,int)

- ea: `0x18001e67c`
- end: `0x18001e7da`
- name: `?SxRegReadDWORD@@YAJPEAUHKEY__@@PEBGPEAKH@Z`
- size: `350`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpValueName, unsigned int *, int)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18001199c`
- `0x1800122b8`
- `0x180013434`
- `0x180016520`

## callees

- `0x18001586c`
- `0x180015974`
- `0x18001e67c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001e731`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001e731`

## string_xrefs

- `0x18001e6a3`: `SxRegReadDWORD`

## pseudocode

```c
__int64 __fastcall SxRegReadDWORD(HKEY hKey, LPCWSTR lpValueName, unsigned int *a3, int a4)
{
  __int16 v8; // ax
  unsigned int v9; // ebx
  int v10; // eax
  __int16 v11; // ax
  BYTE Data[8]; // [rsp+30h] [rbp-40h] BYREF
  int v14; // [rsp+38h] [rbp-38h] BYREF
  __int16 v15; // [rsp+3Ch] [rbp-34h]
  __int16 v16; // [rsp+3Eh] [rbp-32h]
  int v17; // [rsp+40h] [rbp-30h]
  DWORD cbData; // [rsp+98h] [rbp+28h] BYREF
  DWORD Type; // [rsp+A0h] [rbp+30h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v14, "SxRegReadDWORD", 33, 2);
  *(_DWORD *)Data = 0;
  Type = 0;
  cbData = 0;
  if ( a3 )
    *a3 = 0;
  v8 = 42;
  if ( lpValueName && (v15 = 42, v8 = 43, a3) )
  {
    v15 = 43;
    v14 = 0;
    cbData = 4;
    v10 = RegQueryValueExW(hKey, lpValueName, 0, &Type, Data, &cbData);
    if ( a4 && v10 == 2 )
    {
      v9 = 1;
      v14 = 1;
      v11 = 49;
LABEL_19:
      v15 = v11;
      goto LABEL_20;
    }
    if ( v10 > 0 )
      v10 = (unsigned __int16)v10 | 0x80070000;
    v14 = v10;
    if ( v10 < 0 )
    {
      v16 = 52;
      v17 = 1;
      v9 = v10;
      goto LABEL_20;
    }
    v8 = 54;
    v15 = 52;
    if ( Type == 4 )
    {
      v15 = 54;
      if ( cbData == 4 )
      {
        *a3 = *(_DWORD *)Data;
        v11 = 59;
        v9 = 0;
        v14 = 0;
        goto LABEL_19;
      }
      v9 = -2147467259;
      v8 = 55;
    }
    else
    {
      v9 = -2147023267;
    }
  }
  else
  {
    v9 = -2147024809;
  }
  v14 = v9;
  v16 = v8;
LABEL_20:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v14);
  return v9;
}

```

## disassembly

```asm
0x18001e67c  mov     [rsp-18h+arg_0], rbx
0x18001e681  mov     [rsp-18h+arg_18], rsi
0x18001e686  push    rbp
0x18001e687  push    rdi
0x18001e688  push    r14
0x18001e68a  mov     rbp, rsp
0x18001e68d  sub     rsp, 70h
0x18001e691  mov     esi, r9d
0x18001e694  mov     rbx, r8
0x18001e697  mov     r9d, 2; unsigned __int16
0x18001e69d  mov     rdi, rdx
0x18001e6a0  mov     r14, rcx
0x18001e6a3  lea     rdx, aSxregreaddword; "SxRegReadDWORD"
0x18001e6aa  lea     rcx, [rbp+var_38]; this
0x18001e6ae  lea     r8d, [r9+1Fh]; unsigned __int16
0x18001e6b2  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18001e6b7  mov     dword ptr [rbp+Data], 0
0x18001e6be  mov     [rbp+Type], 0
0x18001e6c5  mov     [rbp+cbData], 0
0x18001e6cc  test    rbx, rbx
0x18001e6cf  jz      short loc_18001E6D7
0x18001e6d1  mov     dword ptr [rbx], 0
0x18001e6d7  mov     eax, 2Ah ; '*'
0x18001e6dc  test    rdi, rdi
0x18001e6df  jnz     short loc_18001E6F2
0x18001e6e1  mov     ebx, 80070057h
0x18001e6e6  mov     [rbp+var_38], ebx
0x18001e6e9  mov     [rbp+var_32], ax
0x18001e6ed  jmp     loc_18001E7BA
0x18001e6f2  mov     [rbp+var_34], ax
0x18001e6f6  mov     eax, 2Bh ; '+'
0x18001e6fb  test    rbx, rbx
0x18001e6fe  jz      short loc_18001E6E1
0x18001e700  mov     [rbp+var_34], ax
0x18001e704  lea     r9, [rbp+Type]; lpType
0x18001e708  lea     rax, [rbp+cbData]
0x18001e70c  mov     [rbp+var_38], 0
0x18001e713  mov     [rsp+70h+lpcbData], rax; lpcbData
0x18001e718  xor     r8d, r8d; lpReserved
0x18001e71b  lea     rax, [rbp+Data]
0x18001e71f  mov     [rbp+cbData], 4
0x18001e726  mov     rdx, rdi; lpValueName
0x18001e729  mov     [rsp+70h+lpData], rax; lpData
0x18001e72e  mov     rcx, r14; hKey
0x18001e731  call    cs:__imp_RegQueryValueExW
0x18001e737  test    esi, esi
0x18001e739  jz      short loc_18001E74B
0x18001e73b  cmp     eax, 2
0x18001e73e  jnz     short loc_18001E74B
0x18001e740  lea     ebx, [rax-1]
0x18001e743  mov     [rbp+var_38], ebx
0x18001e746  lea     eax, [rbx+30h]
0x18001e749  jmp     short loc_18001E7B6
0x18001e74b  test    eax, eax
0x18001e74d  jle     short loc_18001E757
0x18001e74f  movzx   eax, ax
0x18001e752  or      eax, 80070000h
0x18001e757  mov     [rbp+var_38], eax
0x18001e75a  mov     ecx, 34h ; '4'
0x18001e75f  test    eax, eax
0x18001e761  jns     short loc_18001E771
0x18001e763  lea     ebx, [rcx-33h]
0x18001e766  mov     [rbp+var_32], cx
0x18001e76a  mov     [rbp+var_30], ebx
0x18001e76d  mov     ebx, eax
0x18001e76f  jmp     short loc_18001E7BA
0x18001e771  cmp     [rbp+Type], 4
0x18001e775  mov     eax, 36h ; '6'
0x18001e77a  mov     [rbp+var_34], cx
0x18001e77e  jz      short loc_18001E78A
0x18001e780  mov     ebx, 8007065Dh
0x18001e785  jmp     loc_18001E6E6
0x18001e78a  cmp     [rbp+cbData], 4
0x18001e78e  mov     [rbp+var_34], ax
0x18001e792  jz      short loc_18001E7A3
0x18001e794  mov     ebx, 80004005h
0x18001e799  mov     eax, 37h ; '7'
0x18001e79e  jmp     loc_18001E6E6
0x18001e7a3  mov     eax, dword ptr [rbp+Data]
0x18001e7a6  mov     [rbx], eax
0x18001e7a8  mov     eax, 3Bh ; ';'
0x18001e7ad  xor     ebx, ebx
0x18001e7af  mov     [rbp+var_38], 0
0x18001e7b6  mov     [rbp+var_34], ax
0x18001e7ba  lea     rcx, [rbp+var_38]; this
0x18001e7be  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18001e7c3  lea     r11, [rsp+70h+var_s0]
0x18001e7c8  mov     eax, ebx
0x18001e7ca  mov     rbx, [r11+20h]
0x18001e7ce  mov     rsi, [r11+38h]
0x18001e7d2  mov     rsp, r11
0x18001e7d5  pop     r14
0x18001e7d7  pop     rdi
0x18001e7d8  pop     rbp
0x18001e7d9  retn
```
