# SxRegReadULONGLONG(HKEY__ *,ushort const *,unsigned __int64 *,int)

- ea: `0x140005ac0`
- end: `0x140005c07`
- name: `?SxRegReadULONGLONG@@YAJPEAUHKEY__@@PEBGPEA_KH@Z`
- size: `327`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpValueName, unsigned __int64 *, DWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1400020c4`
- `0x140003e70`

## callees

- `0x140005ac0`
- `0x14000e324`
- `0x14000e41c`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x140005b6c`
- `ADVAPI32!RegQueryValueExW` at `0x140005b6c`

## string_xrefs

- `0x140005ae3`: `SxRegReadULONGLONG`

## pseudocode

```c
__int64 __fastcall SxRegReadULONGLONG(HKEY hKey, LPCWSTR lpValueName, unsigned __int64 *a3, DWORD a4)
{
  __int64 v7; // rdx
  __int64 v8; // r8
  __int16 v9; // ax
  unsigned int v10; // ebx
  int v11; // eax
  int v13; // [rsp+30h] [rbp-40h] BYREF
  __int16 v14; // [rsp+34h] [rbp-3Ch]
  __int16 v15; // [rsp+36h] [rbp-3Ah]
  int v16; // [rsp+38h] [rbp-38h]
  DWORD cbData; // [rsp+90h] [rbp+20h] BYREF
  unsigned __int64 Data; // [rsp+A0h] [rbp+30h] BYREF
  DWORD Type; // [rsp+A8h] [rbp+38h] BYREF

  Type = a4;
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v13, "SxRegReadULONGLONG", 118, 2);
  Type = 11;
  Data = 0;
  cbData = 8;
  if ( a3 )
    *a3 = 0;
  v9 = 127;
  if ( hKey && (v14 = 127, v9 = 128, a3) )
  {
    v14 = 128;
    v13 = 0;
    v11 = RegQueryValueExW(hKey, lpValueName, 0, &Type, (LPBYTE)&Data, &cbData);
    if ( v11 == 2 )
    {
      v10 = 1;
      v14 = 133;
      v13 = 1;
      goto LABEL_17;
    }
    if ( v11 > 0 )
      v11 = (unsigned __int16)v11 | 0x80070000;
    v13 = v11;
    if ( v11 < 0 )
    {
      v15 = 136;
      v16 = 1;
      v10 = v11;
      goto LABEL_17;
    }
    v9 = 138;
    v14 = 136;
    if ( Type == 11 )
    {
      v14 = 138;
      v9 = 139;
      if ( cbData == 8 )
      {
        v14 = 139;
        *a3 = Data;
        v10 = 0;
        v13 = 0;
        goto LABEL_17;
      }
    }
    v10 = -2147418113;
  }
  else
  {
    v10 = -2147024809;
  }
  v13 = v10;
  v15 = v9;
LABEL_17:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v13, v7, v8);
  return v10;
}

```

## disassembly

```asm
0x140005ac0  mov     [rsp-18h+arg_8], rbx
0x140005ac5  mov     [rsp-18h+Type], r9d
0x140005aca  push    rbp
0x140005acb  push    rsi
0x140005acc  push    rdi
0x140005acd  mov     rbp, rsp
0x140005ad0  sub     rsp, 70h
0x140005ad4  mov     r9d, 2; unsigned __int16
0x140005ada  mov     rbx, r8
0x140005add  mov     rsi, rdx
0x140005ae0  mov     rdi, rcx
0x140005ae3  lea     rdx, aSxregreadulong; "SxRegReadULONGLONG"
0x140005aea  lea     rcx, [rbp+var_40]; this
0x140005aee  lea     r8d, [r9+74h]; unsigned __int16
0x140005af2  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x140005af7  mov     [rbp+Type], 0Bh
0x140005afe  mov     [rbp+Data], 0
0x140005b06  mov     [rbp+cbData], 8
0x140005b0d  test    rbx, rbx
0x140005b10  jz      short loc_140005B19
0x140005b12  mov     qword ptr [rbx], 0
0x140005b19  mov     eax, 7Fh
0x140005b1e  test    rdi, rdi
0x140005b21  jnz     short loc_140005B34
0x140005b23  mov     ebx, 80070057h
0x140005b28  mov     [rbp+var_40], ebx
0x140005b2b  mov     [rbp+var_3A], ax
0x140005b2f  jmp     loc_140005BEC
0x140005b34  mov     [rbp+var_3C], ax
0x140005b38  mov     eax, 80h
0x140005b3d  test    rbx, rbx
0x140005b40  jz      short loc_140005B23
0x140005b42  mov     [rbp+var_3C], ax
0x140005b46  lea     r9, [rbp+Type]; lpType
0x140005b4a  lea     rax, [rbp+cbData]
0x140005b4e  mov     [rbp+var_40], 0
0x140005b55  mov     [rsp+70h+lpcbData], rax; lpcbData
0x140005b5a  xor     r8d, r8d; lpReserved
0x140005b5d  lea     rax, [rbp+Data]
0x140005b61  mov     rdx, rsi; lpValueName
0x140005b64  mov     rcx, rdi; hKey
0x140005b67  mov     [rsp+70h+lpData], rax; lpData
0x140005b6c  call    cs:__imp_RegQueryValueExW
0x140005b72  cmp     eax, 2
0x140005b75  jnz     short loc_140005B88
0x140005b77  lea     ebx, [rax-1]
0x140005b7a  mov     eax, 85h
0x140005b7f  mov     [rbp+var_3C], ax
0x140005b83  mov     [rbp+var_40], ebx
0x140005b86  jmp     short loc_140005BEC
0x140005b88  test    eax, eax
0x140005b8a  jle     short loc_140005B94
0x140005b8c  movzx   eax, ax
0x140005b8f  or      eax, 80070000h
0x140005b94  mov     [rbp+var_40], eax
0x140005b97  mov     ecx, 88h
0x140005b9c  test    eax, eax
0x140005b9e  jns     short loc_140005BB0
0x140005ba0  mov     ebx, 1
0x140005ba5  mov     [rbp+var_3A], cx
0x140005ba9  mov     [rbp+var_38], ebx
0x140005bac  mov     ebx, eax
0x140005bae  jmp     short loc_140005BEC
0x140005bb0  cmp     [rbp+Type], 0Bh
0x140005bb4  mov     eax, 8Ah
0x140005bb9  mov     [rbp+var_3C], cx
0x140005bbd  jz      short loc_140005BC9
0x140005bbf  mov     ebx, 8000FFFFh
0x140005bc4  jmp     loc_140005B28
0x140005bc9  cmp     [rbp+cbData], 8
0x140005bcd  mov     [rbp+var_3C], ax
0x140005bd1  mov     eax, 8Bh
0x140005bd6  jnz     short loc_140005BBF
0x140005bd8  mov     [rbp+var_3C], ax
0x140005bdc  mov     rax, [rbp+Data]
0x140005be0  mov     [rbx], rax
0x140005be3  xor     ebx, ebx
0x140005be5  mov     [rbp+var_40], 0
0x140005bec  lea     rcx, [rbp+var_40]; this
0x140005bf0  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x140005bf5  mov     eax, ebx
0x140005bf7  mov     rbx, [rsp+70h+arg_8]
0x140005bff  add     rsp, 70h
0x140005c03  pop     rdi
0x140005c04  pop     rsi
0x140005c05  pop     rbp
0x140005c06  retn
```
