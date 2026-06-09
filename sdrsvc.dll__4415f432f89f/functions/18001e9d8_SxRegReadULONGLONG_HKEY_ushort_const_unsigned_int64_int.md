# SxRegReadULONGLONG(HKEY__ *,ushort const *,unsigned __int64 *,int)

- ea: `0x18001e9d8`
- end: `0x18001eb1f`
- name: `?SxRegReadULONGLONG@@YAJPEAUHKEY__@@PEBGPEA_KH@Z`
- size: `327`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpValueName, unsigned __int64 *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180013434`

## callees

- `0x18001586c`
- `0x180015974`
- `0x18001e9d8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001ea84`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001ea84`

## string_xrefs

- `0x18001e9fb`: `SxRegReadULONGLONG`

## pseudocode

```c
__int64 __fastcall SxRegReadULONGLONG(HKEY hKey, LPCWSTR lpValueName, unsigned __int64 *a3, DWORD a4)
{
  __int16 v7; // ax
  unsigned int v8; // ebx
  int v9; // eax
  int v11; // [rsp+30h] [rbp-40h] BYREF
  __int16 v12; // [rsp+34h] [rbp-3Ch]
  __int16 v13; // [rsp+36h] [rbp-3Ah]
  int v14; // [rsp+38h] [rbp-38h]
  DWORD cbData; // [rsp+90h] [rbp+20h] BYREF
  unsigned __int64 Data; // [rsp+A0h] [rbp+30h] BYREF
  DWORD Type; // [rsp+A8h] [rbp+38h] BYREF

  Type = a4;
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v11, "SxRegReadULONGLONG", 118, 2);
  Type = 11;
  Data = 0;
  cbData = 8;
  if ( a3 )
    *a3 = 0;
  v7 = 127;
  if ( hKey && (v12 = 127, v7 = 128, a3) )
  {
    v12 = 128;
    v11 = 0;
    v9 = RegQueryValueExW(hKey, lpValueName, 0, &Type, (LPBYTE)&Data, &cbData);
    if ( v9 == 2 )
    {
      v8 = 1;
      v12 = 133;
      v11 = 1;
      goto LABEL_17;
    }
    if ( v9 > 0 )
      v9 = (unsigned __int16)v9 | 0x80070000;
    v11 = v9;
    if ( v9 < 0 )
    {
      v13 = 136;
      v14 = 1;
      v8 = v9;
      goto LABEL_17;
    }
    v7 = 138;
    v12 = 136;
    if ( Type == 11 )
    {
      v12 = 138;
      v7 = 139;
      if ( cbData == 8 )
      {
        v12 = 139;
        *a3 = Data;
        v8 = 0;
        v11 = 0;
        goto LABEL_17;
      }
    }
    v8 = -2147418113;
  }
  else
  {
    v8 = -2147024809;
  }
  v11 = v8;
  v13 = v7;
LABEL_17:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v11);
  return v8;
}

```

## disassembly

```asm
0x18001e9d8  mov     [rsp-18h+arg_8], rbx
0x18001e9dd  mov     [rsp-18h+Type], r9d
0x18001e9e2  push    rbp
0x18001e9e3  push    rsi
0x18001e9e4  push    rdi
0x18001e9e5  mov     rbp, rsp
0x18001e9e8  sub     rsp, 70h
0x18001e9ec  mov     r9d, 2; unsigned __int16
0x18001e9f2  mov     rbx, r8
0x18001e9f5  mov     rsi, rdx
0x18001e9f8  mov     rdi, rcx
0x18001e9fb  lea     rdx, aSxregreadulong; "SxRegReadULONGLONG"
0x18001ea02  lea     rcx, [rbp+var_40]; this
0x18001ea06  lea     r8d, [r9+74h]; unsigned __int16
0x18001ea0a  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18001ea0f  mov     [rbp+Type], 0Bh
0x18001ea16  mov     [rbp+Data], 0
0x18001ea1e  mov     [rbp+cbData], 8
0x18001ea25  test    rbx, rbx
0x18001ea28  jz      short loc_18001EA31
0x18001ea2a  mov     qword ptr [rbx], 0
0x18001ea31  mov     eax, 7Fh
0x18001ea36  test    rdi, rdi
0x18001ea39  jnz     short loc_18001EA4C
0x18001ea3b  mov     ebx, 80070057h
0x18001ea40  mov     [rbp+var_40], ebx
0x18001ea43  mov     [rbp+var_3A], ax
0x18001ea47  jmp     loc_18001EB04
0x18001ea4c  mov     [rbp+var_3C], ax
0x18001ea50  mov     eax, 80h
0x18001ea55  test    rbx, rbx
0x18001ea58  jz      short loc_18001EA3B
0x18001ea5a  mov     [rbp+var_3C], ax
0x18001ea5e  lea     r9, [rbp+Type]; lpType
0x18001ea62  lea     rax, [rbp+cbData]
0x18001ea66  mov     [rbp+var_40], 0
0x18001ea6d  mov     [rsp+70h+lpcbData], rax; lpcbData
0x18001ea72  xor     r8d, r8d; lpReserved
0x18001ea75  lea     rax, [rbp+Data]
0x18001ea79  mov     rdx, rsi; lpValueName
0x18001ea7c  mov     rcx, rdi; hKey
0x18001ea7f  mov     [rsp+70h+lpData], rax; lpData
0x18001ea84  call    cs:__imp_RegQueryValueExW
0x18001ea8a  cmp     eax, 2
0x18001ea8d  jnz     short loc_18001EAA0
0x18001ea8f  lea     ebx, [rax-1]
0x18001ea92  mov     eax, 85h
0x18001ea97  mov     [rbp+var_3C], ax
0x18001ea9b  mov     [rbp+var_40], ebx
0x18001ea9e  jmp     short loc_18001EB04
0x18001eaa0  test    eax, eax
0x18001eaa2  jle     short loc_18001EAAC
0x18001eaa4  movzx   eax, ax
0x18001eaa7  or      eax, 80070000h
0x18001eaac  mov     [rbp+var_40], eax
0x18001eaaf  mov     ecx, 88h
0x18001eab4  test    eax, eax
0x18001eab6  jns     short loc_18001EAC8
0x18001eab8  mov     ebx, 1
0x18001eabd  mov     [rbp+var_3A], cx
0x18001eac1  mov     [rbp+var_38], ebx
0x18001eac4  mov     ebx, eax
0x18001eac6  jmp     short loc_18001EB04
0x18001eac8  cmp     [rbp+Type], 0Bh
0x18001eacc  mov     eax, 8Ah
0x18001ead1  mov     [rbp+var_3C], cx
0x18001ead5  jz      short loc_18001EAE1
0x18001ead7  mov     ebx, 8000FFFFh
0x18001eadc  jmp     loc_18001EA40
0x18001eae1  cmp     [rbp+cbData], 8
0x18001eae5  mov     [rbp+var_3C], ax
0x18001eae9  mov     eax, 8Bh
0x18001eaee  jnz     short loc_18001EAD7
0x18001eaf0  mov     [rbp+var_3C], ax
0x18001eaf4  mov     rax, [rbp+Data]
0x18001eaf8  mov     [rbx], rax
0x18001eafb  xor     ebx, ebx
0x18001eafd  mov     [rbp+var_40], 0
0x18001eb04  lea     rcx, [rbp+var_40]; this
0x18001eb08  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18001eb0d  mov     eax, ebx
0x18001eb0f  mov     rbx, [rsp+70h+arg_8]
0x18001eb17  add     rsp, 70h
0x18001eb1b  pop     rdi
0x18001eb1c  pop     rsi
0x18001eb1d  pop     rbp
0x18001eb1e  retn
```
