# CRegistry::GetValue(ushort const *,CBuffer &,ulong *)

- ea: `0x18000d320`
- end: `0x18000d54d`
- name: `?GetValue@CRegistry@@QEAAXPEBGAEAVCBuffer@@PEAK@Z`
- size: `557`
- prototype: `void __fastcall(CRegistry *__hidden this, const unsigned __int16 *, struct CBuffer *, unsigned int *)`
- caller_count: `5`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callers

- `0x180001cfc`
- `0x18000cd90`
- `0x180010400`
- `0x18001703c`
- `0x18002a7d8`

## callees

- `0x18000d320`
- `0x18001b9b8`
- `0x18001ba04`
- `0x18002ef20`
- `0x18002ef38`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000d3a1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000d3a1`

## pseudocode

```c
void __fastcall CRegistry::GetValue(CRegistry *this, const unsigned __int16 *a2, struct CBuffer *a3, unsigned int *a4)
{
  ulong v4; // eax
  int v8; // esi
  DWORD *v9; // r14
  BYTE *lpData; // rax
  LSTATUS v11; // eax
  DWORD v12; // edi
  void *v13; // rsi
  void *v14; // rcx
  void *v15; // rax
  void *v16; // rsi
  DWORD v17; // edi
  void *v18; // rbp
  void *v19; // rcx
  DWORD Type; // [rsp+30h] [rbp-48h] BYREF
  ulong pExceptionObject[3]; // [rsp+34h] [rbp-44h] BYREF
  DWORD cbData; // [rsp+80h] [rbp+8h] BYREF
  const unsigned __int16 *v23; // [rsp+88h] [rbp+10h]

  v23 = a2;
  v4 = *((_DWORD *)this + 10);
  Type = 0;
  if ( v4 )
  {
    pExceptionObject[0] = v4;
    throw pExceptionObject;
  }
  v8 = 0;
  v9 = (DWORD *)((char *)a3 + 16);
  while ( !v8 )
  {
    cbData = *((_DWORD *)a3 + 5);
    if ( cbData )
    {
      lpData = (BYTE *)*((_QWORD *)a3 + 1);
      v9 = (DWORD *)((char *)a3 + 16);
    }
    else
    {
      lpData = (BYTE *)&WideCharStr;
    }
    v11 = RegQueryValueExW(*(HKEY *)this, a2, 0, &Type, lpData, &cbData);
    if ( v11 )
    {
      if ( v11 != 234 )
      {
        pExceptionObject[0] = v11;
        throw pExceptionObject;
      }
      v17 = cbData;
      if ( *((_DWORD *)a3 + 5) < cbData )
      {
        v18 = operator new[](cbData);
        if ( !v18 )
        {
          pExceptionObject[0] = 14;
          throw pExceptionObject;
        }
        v19 = (void *)*((_QWORD *)a3 + 1);
        if ( v19 )
          operator delete(v19);
        *((_QWORD *)a3 + 1) = v18;
        *((_DWORD *)a3 + 5) = v17;
      }
      *v9 = 0;
      a2 = v23;
    }
    else
    {
      v12 = cbData;
      if ( *v9 )
      {
        if ( *((_DWORD *)a3 + 5) >= cbData )
          goto LABEL_14;
        v15 = operator new[](cbData);
        v16 = v15;
        if ( !v15 )
        {
          pExceptionObject[0] = 14;
          throw pExceptionObject;
        }
        memcpy_0(v15, *((const void **)a3 + 1), *v9);
        operator delete(*((void **)a3 + 1));
        *((_QWORD *)a3 + 1) = v16;
        v8 = 1;
        *((_DWORD *)a3 + 5) = v12;
        *v9 = v12;
        a2 = v23;
      }
      else
      {
        if ( *((_DWORD *)a3 + 5) < cbData )
        {
          v13 = operator new[](cbData);
          if ( !v13 )
          {
            pExceptionObject[0] = 14;
            throw pExceptionObject;
          }
          v14 = (void *)*((_QWORD *)a3 + 1);
          if ( v14 )
            operator delete(v14);
          *((_QWORD *)a3 + 1) = v13;
          *((_DWORD *)a3 + 5) = v12;
        }
        *v9 = 0;
LABEL_14:
        *v9 = v12;
        v8 = 1;
        a2 = v23;
      }
    }
  }
  if ( a4 )
    *a4 = Type;
}

```

## disassembly

```asm
0x18000d320  mov     r11, rsp
0x18000d323  mov     [r11+10h], rdx
0x18000d327  push    rbx
0x18000d328  push    rbp
0x18000d329  push    r12
0x18000d32b  push    r13
0x18000d32d  sub     rsp, 58h
0x18000d331  mov     eax, [rcx+28h]
0x18000d334  xor     ebp, ebp
0x18000d336  mov     [rsp+78h+Type], ebp
0x18000d33a  mov     r12, r9
0x18000d33d  mov     rbx, r8
0x18000d340  mov     r13, rcx
0x18000d343  test    eax, eax
0x18000d345  jnz     loc_18000D4E9
0x18000d34b  mov     [r11+18h], rsi
0x18000d34f  mov     esi, ebp
0x18000d351  mov     [r11-30h], r14
0x18000d355  lea     r14, [r8+10h]
0x18000d359  mov     [r11-38h], r15
0x18000d35d  mov     [r11-28h], rdi
0x18000d361  test    esi, esi
0x18000d363  jnz     loc_18000D400
0x18000d369  mov     eax, [rbx+14h]
0x18000d36c  mov     [rsp+78h+cbData], eax
0x18000d373  test    eax, eax
0x18000d375  jz      loc_18000D4C7
0x18000d37b  mov     rax, [rbx+8]
0x18000d37f  lea     r14, [rbx+10h]
0x18000d383  lea     rcx, [rsp+78h+cbData]
0x18000d38b  xor     r8d, r8d; lpReserved
0x18000d38e  mov     [rsp+78h+lpcbData], rcx; lpcbData
0x18000d393  lea     r9, [rsp+78h+Type]; lpType
0x18000d398  mov     rcx, [r13+0]; hKey
0x18000d39c  mov     [rsp+78h+lpData], rax; lpData
0x18000d3a1  call    cs:__imp_RegQueryValueExW
0x18000d3a7  test    eax, eax
0x18000d3a9  jnz     loc_18000D47C
0x18000d3af  mov     edi, [rsp+78h+cbData]
0x18000d3b6  cmp     [r14], eax
0x18000d3b9  ja      short loc_18000D42F
0x18000d3bb  cmp     [rbx+14h], edi
0x18000d3be  jnb     short loc_18000D3E8
0x18000d3c0  mov     ecx, edi; unsigned __int64
0x18000d3c2  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000d3c7  mov     rsi, rax
0x18000d3ca  test    rax, rax
0x18000d3cd  jz      loc_18000D533
0x18000d3d3  mov     rcx, [rbx+8]; void *
0x18000d3d7  test    rcx, rcx
0x18000d3da  jz      short loc_18000D3E1
0x18000d3dc  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000d3e1  mov     [rbx+8], rsi
0x18000d3e5  mov     [rbx+14h], edi
0x18000d3e8  mov     [r14], ebp
0x18000d3eb  mov     [r14], edi
0x18000d3ee  mov     esi, 1
0x18000d3f3  mov     rdx, [rsp+78h+arg_8]
0x18000d3fb  jmp     loc_18000D361
0x18000d400  test    r12, r12
0x18000d403  jz      short loc_18000D40D
0x18000d405  mov     eax, [rsp+78h+Type]
0x18000d409  mov     [r12], eax
0x18000d40d  mov     rdi, [rsp+78h+var_28]
0x18000d412  mov     r14, [rsp+78h+var_30]
0x18000d417  mov     rsi, [rsp+78h+arg_10]
0x18000d41f  mov     r15, [rsp+78h+var_38]
0x18000d424  add     rsp, 58h
0x18000d428  pop     r13
0x18000d42a  pop     r12
0x18000d42c  pop     rbp
0x18000d42d  pop     rbx
0x18000d42e  retn
0x18000d42f  cmp     [rbx+14h], edi
0x18000d432  jnb     short loc_18000D3EB
0x18000d434  mov     rcx, rdi; unsigned __int64
0x18000d437  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000d43c  mov     rsi, rax
0x18000d43f  test    rax, rax
0x18000d442  jz      loc_18000D519
0x18000d448  mov     r8d, [r14]; Size
0x18000d44b  mov     rcx, rax; void *
0x18000d44e  mov     rdx, [rbx+8]; Src
0x18000d452  call    memcpy_0
0x18000d457  mov     rcx, [rbx+8]; void *
0x18000d45b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000d460  mov     [rbx+8], rsi
0x18000d464  mov     esi, 1
0x18000d469  mov     [rbx+14h], edi
0x18000d46c  mov     [r14], edi
0x18000d46f  mov     rdx, [rsp+78h+arg_8]
0x18000d477  jmp     loc_18000D361
0x18000d47c  cmp     eax, 0EAh
0x18000d481  jnz     short loc_18000D4D3
0x18000d483  mov     edi, [rsp+78h+cbData]
0x18000d48a  cmp     [rbx+14h], edi
0x18000d48d  jnb     short loc_18000D4B5
0x18000d48f  mov     ecx, edi; unsigned __int64
0x18000d491  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000d496  mov     rbp, rax
0x18000d499  test    rax, rax
0x18000d49c  jz      short loc_18000D4FF
0x18000d49e  mov     rcx, [rbx+8]; void *
0x18000d4a2  test    rcx, rcx
0x18000d4a5  jz      short loc_18000D4AC
0x18000d4a7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000d4ac  mov     [rbx+8], rbp
0x18000d4b0  xor     ebp, ebp
0x18000d4b2  mov     [rbx+14h], edi
0x18000d4b5  mov     [r14], ebp
0x18000d4b8  mov     edi, ebp
0x18000d4ba  mov     rdx, [rsp+78h+arg_8]
0x18000d4c2  jmp     loc_18000D361
0x18000d4c7  lea     rax, WideCharStr
0x18000d4ce  jmp     loc_18000D383
0x18000d4d3  lea     rdx, _TI1K; pThrowInfo
0x18000d4da  mov     [rsp+78h+pExceptionObject], eax
0x18000d4de  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x18000d4e3  call    _CxxThrowException_0
0x18000d4e9  lea     rdx, _TI1K; pThrowInfo
0x18000d4f0  mov     [rsp+78h+pExceptionObject], eax
0x18000d4f4  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x18000d4f9  call    _CxxThrowException_0
0x18000d4ff  lea     rdx, _TI1K; pThrowInfo
0x18000d506  mov     [rsp+78h+pExceptionObject], 0Eh
0x18000d50e  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x18000d513  call    _CxxThrowException_0
0x18000d519  lea     rdx, _TI1K; pThrowInfo
0x18000d520  mov     [rsp+78h+pExceptionObject], 0Eh
0x18000d528  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x18000d52d  call    _CxxThrowException_0
0x18000d533  lea     rdx, _TI1K; pThrowInfo
0x18000d53a  mov     [rsp+78h+pExceptionObject], 0Eh
0x18000d542  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x18000d547  call    _CxxThrowException_0
```
