# SxRegReadMultiString(HKEY__ *,ushort const *,ushort * *)

- ea: `0x18002e410`
- end: `0x18002e539`
- name: `?SxRegReadMultiString@@YAJPEAUHKEY__@@PEBGPEAPEAG@Z`
- size: `297`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpValueName, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001be74`

## callees

- `0x1800268b4`
- `0x1800269ac`
- `0x18002e410`
- `0x18002e540`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e510`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e510`

## string_xrefs

- `0x18002e42e`: `SxRegReadMultiString`

## pseudocode

```c
__int64 __fastcall SxRegReadMultiString(HKEY hKey, LPCWSTR lpValueName, unsigned __int8 **a3)
{
  unsigned __int8 *v6; // r9
  __int16 v7; // ax
  int v8; // eax
  bool v9; // sf
  unsigned int v10; // edx
  unsigned int v11; // ebx
  __int64 v12; // rdx
  __int64 v13; // r8
  int v15; // [rsp+20h] [rbp-40h] BYREF
  __int16 v16; // [rsp+24h] [rbp-3Ch]
  __int16 v17; // [rsp+26h] [rbp-3Ah]
  int v18; // [rsp+28h] [rbp-38h]
  unsigned int v19; // [rsp+88h] [rbp+28h] BYREF
  unsigned __int8 *v20; // [rsp+90h] [rbp+30h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v15, "SxRegReadMultiString", 393, 2);
  v20 = 0;
  v6 = 0;
  v19 = 0;
  if ( a3 )
    *a3 = 0;
  v7 = 402;
  if ( !lpValueName || (v16 = 402, v7 = 403, !a3) )
  {
    v15 = -2147024809;
LABEL_15:
    v17 = v7;
    goto LABEL_16;
  }
  v15 = 0;
  v16 = 403;
  v8 = SxRegReadMultiStringAsBlob(hKey, lpValueName, &v20, &v19);
  v6 = v20;
  v9 = v8 < 0;
  v15 = v8;
  v7 = 405;
  if ( v9 )
  {
    v18 = 1;
    goto LABEL_15;
  }
  v16 = 405;
  v7 = 410;
  if ( (v19 & 1) != 0 )
  {
LABEL_14:
    v15 = -2147418113;
    goto LABEL_15;
  }
  v10 = v19 >> 1;
  v15 = 0;
  v16 = 410;
  if ( v19 >> 1 < 3 || *(_WORD *)&v20[2 * v10 - 2] || *(_WORD *)&v20[2 * v10 - 4] )
  {
    v7 = 418;
    goto LABEL_14;
  }
  *a3 = v20;
  v16 = 418;
  v6 = 0;
LABEL_16:
  CoTaskMemFree(v6);
  v11 = v15;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v15, v12, v13);
  return v11;
}

```

## disassembly

```asm
0x18002e410  mov     [rsp-18h+arg_0], rbx
0x18002e415  mov     [rsp-18h+arg_18], rsi
0x18002e41a  push    rbp
0x18002e41b  push    rdi
0x18002e41c  push    r14
0x18002e41e  mov     rbp, rsp
0x18002e421  sub     rsp, 60h
0x18002e425  mov     rbx, r8
0x18002e428  mov     rdi, rdx
0x18002e42b  mov     rsi, rcx
0x18002e42e  lea     rdx, aSxregreadmulti; "SxRegReadMultiString"
0x18002e435  mov     r8d, 189h; unsigned __int16
0x18002e43b  lea     rcx, [rbp+var_40]; this
0x18002e43f  mov     r9d, 2; unsigned __int16
0x18002e445  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18002e44a  xor     r14d, r14d
0x18002e44d  mov     [rbp+arg_10], r14
0x18002e451  mov     r9d, r14d
0x18002e454  mov     [rbp+arg_8], r14d
0x18002e458  test    rbx, rbx
0x18002e45b  jz      short loc_18002E460
0x18002e45d  mov     [rbx], r14
0x18002e460  mov     eax, 192h
0x18002e465  test    rdi, rdi
0x18002e468  jnz     short loc_18002E476
0x18002e46a  mov     [rbp+var_40], 80070057h
0x18002e471  jmp     loc_18002E509
0x18002e476  mov     [rbp+var_3C], ax
0x18002e47a  mov     eax, 193h
0x18002e47f  test    rbx, rbx
0x18002e482  jz      short loc_18002E46A
0x18002e484  lea     r9, [rbp+arg_8]; unsigned int *
0x18002e488  mov     [rbp+var_40], r14d
0x18002e48c  lea     r8, [rbp+arg_10]; unsigned __int8 **
0x18002e490  mov     [rbp+var_3C], ax
0x18002e494  mov     rdx, rdi; lpValueName
0x18002e497  mov     rcx, rsi; hKey
0x18002e49a  call    ?SxRegReadMultiStringAsBlob@@YAJPEAUHKEY__@@PEBGPEAPEAEPEAK@Z; SxRegReadMultiStringAsBlob(HKEY__ *,ushort const *,uchar * *,ulong *)
0x18002e49f  mov     r9, [rbp+arg_10]
0x18002e4a3  test    eax, eax
0x18002e4a5  mov     [rbp+var_40], eax
0x18002e4a8  mov     eax, 195h
0x18002e4ad  jns     short loc_18002E4B8
0x18002e4af  mov     [rbp+var_38], 1
0x18002e4b6  jmp     short loc_18002E509
0x18002e4b8  mov     edx, [rbp+arg_8]
0x18002e4bb  mov     [rbp+var_3C], ax
0x18002e4bf  mov     eax, 19Ah
0x18002e4c4  test    dl, 1
0x18002e4c7  jnz     short loc_18002E502
0x18002e4c9  shr     edx, 1
0x18002e4cb  mov     [rbp+var_40], r14d
0x18002e4cf  mov     [rbp+var_3C], ax
0x18002e4d3  cmp     edx, 3
0x18002e4d6  jb      short loc_18002E4FD
0x18002e4d8  lea     eax, [rdx-1]
0x18002e4db  cmp     [r9+rax*2], r14w
0x18002e4e0  jnz     short loc_18002E4FD
0x18002e4e2  lea     eax, [rdx-2]
0x18002e4e5  cmp     [r9+rax*2], r14w
0x18002e4ea  jnz     short loc_18002E4FD
0x18002e4ec  mov     eax, 1A2h
0x18002e4f1  mov     [rbx], r9
0x18002e4f4  mov     [rbp+var_3C], ax
0x18002e4f8  mov     r9, r14
0x18002e4fb  jmp     short loc_18002E50D
0x18002e4fd  mov     eax, 1A2h
0x18002e502  mov     [rbp+var_40], 8000FFFFh
0x18002e509  mov     [rbp+var_3A], ax
0x18002e50d  mov     rcx, r9; pv
0x18002e510  call    cs:__imp_CoTaskMemFree
0x18002e516  mov     ebx, [rbp+var_40]
0x18002e519  lea     rcx, [rbp+var_40]; this
0x18002e51d  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18002e522  lea     r11, [rsp+60h+var_s0]
0x18002e527  mov     eax, ebx
0x18002e529  mov     rbx, [r11+20h]
0x18002e52d  mov     rsi, [r11+38h]
0x18002e531  mov     rsp, r11
0x18002e534  pop     r14
0x18002e536  pop     rdi
0x18002e537  pop     rbp
0x18002e538  retn
```
