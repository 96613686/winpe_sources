# CSrDrvWuHelper::_EnumDriverWUNameCollector(void *,_SX_WU_DRIVER_ENUM_STATUS,ushort *)

- ea: `0x18000c100`
- end: `0x18000c251`
- name: `?_EnumDriverWUNameCollector@CSrDrvWuHelper@@CAJPEAXW4_SX_WU_DRIVER_ENUM_STATUS@@PEAG@Z`
- size: `337`
- prototype: `__int64 __fastcall(__int64 *, int, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x18000c100`
- `0x18000e330`
- `0x180016010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18000c1df`
- `ole32!CoTaskMemFree` at `0x18000c20e`
- `ole32!CoTaskMemFree` at `0x18000c1df`
- `ole32!CoTaskMemFree` at `0x18000c20e`
- `ole32!CoTaskMemRealloc` at `0x18000c1bd`
- `ole32!CoTaskMemRealloc` at `0x18000c1bd`

## pseudocode

```c
__int64 __fastcall CSrDrvWuHelper::_EnumDriverWUNameCollector(__int64 *a1, int a2, const unsigned __int16 *a3)
{
  __int64 v3; // r14
  unsigned int v4; // r9d
  int v5; // edx
  __int64 v6; // rbp
  __int64 result; // rax
  unsigned int v8; // eax
  unsigned int v9; // esi
  int v10; // edi
  unsigned int v11; // ebx
  LPVOID v12; // rax
  LPVOID pv; // [rsp+40h] [rbp+8h] BYREF

  v3 = a1[1];
  v4 = 3;
  pv = 0;
  if ( a2 )
  {
    v5 = a2 - 1;
    if ( v5 )
    {
      if ( v5 != 1 )
        goto LABEL_25;
      v6 = *a1;
      result = SxCopyString(a3, (unsigned __int16 **)&pv);
      if ( (int)result < 0 )
        return result;
      v8 = *(_DWORD *)(v6 + 16);
      v9 = v8 + 1;
      if ( v8 + 1 < v8 )
      {
        v10 = -2147024362;
      }
      else
      {
        v10 = 0;
        if ( v9 > *(_DWORD *)(v6 + 20) )
        {
          v11 = 64;
          if ( v9 > 0x40 )
          {
            v11 = 256;
            if ( v9 > 0x100 )
            {
              v11 = 1024;
              if ( v9 > 0x400 )
              {
                v11 = 4096;
                if ( v9 > 0x1000 )
                {
                  v11 = 0x4000;
                  if ( v9 > 0x4000 )
                  {
                    v11 = (v8 + 0x10000) & 0xFFFF0000;
                    if ( v11 < v9 )
                      v11 = v8 + 1;
                  }
                }
              }
            }
          }
          if ( is_mul_ok(v11, 8u) )
          {
            v12 = CoTaskMemRealloc(*(LPVOID *)(v6 + 8), 8LL * v11);
            if ( v12 )
            {
              *(_QWORD *)(v6 + 8) = v12;
              *(_DWORD *)(v6 + 20) = v11;
            }
            else
            {
              v10 = -2147024882;
            }
          }
          else
          {
            v10 = -2147024362;
          }
        }
        CoTaskMemFree(0);
        if ( v10 >= 0 )
        {
          v4 = 2;
          *(_QWORD *)(*(_QWORD *)(v6 + 8) + 8LL * *(unsigned int *)(v6 + 16)) = pv;
          *(_DWORD *)(v6 + 16) = v9;
          goto LABEL_25;
        }
      }
      CoTaskMemFree(pv);
      return (unsigned int)v10;
    }
    v4 = 1;
  }
  else
  {
    v4 = 0;
  }
LABEL_25:
  if ( v3 )
    return (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v3 + 24LL))(v3, v4);
  else
    return 0;
}

```

## disassembly

```asm
0x18000c100  mov     rax, rsp
0x18000c103  mov     [rax+10h], rbx
0x18000c107  mov     [rax+18h], rbp
0x18000c10b  push    rsi
0x18000c10c  push    rdi
0x18000c10d  push    r14
0x18000c10f  sub     rsp, 20h
0x18000c113  mov     r14, [rcx+8]
0x18000c117  mov     r9d, 3
0x18000c11d  mov     qword ptr [rax+8], 0
0x18000c125  test    edx, edx
0x18000c127  jz      loc_18000C220
0x18000c12d  sub     edx, 1
0x18000c130  jz      loc_18000C218
0x18000c136  cmp     edx, 1
0x18000c139  jnz     loc_18000C223
0x18000c13f  mov     rbp, [rcx]
0x18000c142  lea     rdx, [rax+8]; unsigned __int16 **
0x18000c146  mov     rcx, r8; Src
0x18000c149  call    ?SxCopyString@@YAJPEBGPEAPEAG@Z; SxCopyString(ushort const *,ushort * *)
0x18000c14e  test    eax, eax
0x18000c150  js      loc_18000C23E
0x18000c156  mov     eax, [rbp+10h]
0x18000c159  lea     esi, [rax+1]
0x18000c15c  cmp     esi, eax
0x18000c15e  jb      loc_18000C204
0x18000c164  xor     edi, edi
0x18000c166  cmp     esi, [rbp+14h]
0x18000c169  jbe     short loc_18000C1DD
0x18000c16b  lea     ebx, [rdi+40h]
0x18000c16e  cmp     esi, ebx
0x18000c170  jbe     short loc_18000C1A7
0x18000c172  mov     ebx, 100h
0x18000c177  cmp     esi, ebx
0x18000c179  jbe     short loc_18000C1A7
0x18000c17b  mov     ebx, 400h
0x18000c180  cmp     esi, ebx
0x18000c182  jbe     short loc_18000C1A7
0x18000c184  mov     ebx, 1000h
0x18000c189  cmp     esi, ebx
0x18000c18b  jbe     short loc_18000C1A7
0x18000c18d  mov     ebx, 4000h
0x18000c192  cmp     esi, ebx
0x18000c194  jbe     short loc_18000C1A7
0x18000c196  lea     ebx, [rsi+0FFFFh]
0x18000c19c  and     ebx, 0FFFF0000h
0x18000c1a2  cmp     ebx, esi
0x18000c1a4  cmovb   ebx, esi
0x18000c1a7  mov     ecx, ebx
0x18000c1a9  mov     eax, 8
0x18000c1ae  mul     rcx
0x18000c1b1  test    rdx, rdx
0x18000c1b4  jnz     short loc_18000C1D8
0x18000c1b6  mov     rcx, [rbp+8]; pv
0x18000c1ba  mov     rdx, rax; cb
0x18000c1bd  call    cs:__imp_CoTaskMemRealloc
0x18000c1c3  test    rax, rax
0x18000c1c6  jnz     short loc_18000C1CF
0x18000c1c8  mov     edi, 8007000Eh
0x18000c1cd  jmp     short loc_18000C1DD
0x18000c1cf  mov     [rbp+8], rax
0x18000c1d3  mov     [rbp+14h], ebx
0x18000c1d6  jmp     short loc_18000C1DD
0x18000c1d8  mov     edi, 80070216h
0x18000c1dd  xor     ecx, ecx; pv
0x18000c1df  call    cs:__imp_CoTaskMemFree
0x18000c1e5  test    edi, edi
0x18000c1e7  js      short loc_18000C209
0x18000c1e9  mov     edx, [rbp+10h]
0x18000c1ec  mov     r9d, 2
0x18000c1f2  mov     rcx, [rbp+8]
0x18000c1f6  mov     rax, [rsp+38h+pv]
0x18000c1fb  mov     [rcx+rdx*8], rax
0x18000c1ff  mov     [rbp+10h], esi
0x18000c202  jmp     short loc_18000C223
0x18000c204  mov     edi, 80070216h
0x18000c209  mov     rcx, [rsp+38h+pv]; pv
0x18000c20e  call    cs:__imp_CoTaskMemFree
0x18000c214  mov     eax, edi
0x18000c216  jmp     short loc_18000C23E
0x18000c218  mov     r9d, 1
0x18000c21e  jmp     short loc_18000C223
0x18000c220  xor     r9d, r9d
0x18000c223  test    r14, r14
0x18000c226  jz      short loc_18000C23C
0x18000c228  mov     rax, [r14]
0x18000c22b  mov     edx, r9d
0x18000c22e  mov     rcx, r14
0x18000c231  mov     rax, [rax+18h]
0x18000c235  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c23a  jmp     short loc_18000C23E
0x18000c23c  xor     eax, eax
0x18000c23e  mov     rbx, [rsp+38h+arg_8]
0x18000c243  mov     rbp, [rsp+38h+arg_10]
0x18000c248  add     rsp, 20h
0x18000c24c  pop     r14
0x18000c24e  pop     rdi
0x18000c24f  pop     rsi
0x18000c250  retn
```
