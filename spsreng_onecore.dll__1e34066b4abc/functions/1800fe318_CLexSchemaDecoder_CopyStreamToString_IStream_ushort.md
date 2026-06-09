# CLexSchemaDecoder::CopyStreamToString(IStream *,ushort * *)

- ea: `0x1800fe318`
- end: `0x1800fe40e`
- name: `?CopyStreamToString@CLexSchemaDecoder@@CAJPEAUIStream@@PEAPEAG@Z`
- size: `246`
- prototype: `__int64 __fastcall(struct IStream *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800fe540`

## callees

- `0x1800fe318`
- `0x180102010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800fe3ab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800fe3ab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800fe38e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800fe38e`

## pseudocode

```c
__int64 __fastcall CLexSchemaDecoder::CopyStreamToString(struct IStream *a1, unsigned __int16 **a2)
{
  struct IStreamVtbl *lpVtbl; // rax
  unsigned __int16 *v4; // rdi
  int v6; // ebx
  __int64 v7; // rsi
  struct IStreamVtbl *v9; // rax
  __int64 v10; // [rsp+50h] [rbp+8h] BYREF
  __int64 v11; // [rsp+60h] [rbp+18h] BYREF

  lpVtbl = a1->lpVtbl;
  v10 = 0;
  v4 = 0;
  v11 = 0;
  v6 = ((__int64 (__fastcall *)(struct IStream *, _QWORD, __int64, __int64 *))lpVtbl->Seek)(a1, 0, 2, &v11);
  if ( v6 >= 0 )
  {
    v6 = ((__int64 (__fastcall *)(struct IStream *, __int64, _QWORD, _QWORD))a1->lpVtbl->Seek)(a1, v10, 0, 0);
    if ( v6 >= 0 )
    {
      v7 = (unsigned int)v11 >> 1;
      v4 = (unsigned __int16 *)CoTaskMemAlloc(2LL * (unsigned int)(v7 + 1));
      if ( v4 )
      {
        v9 = a1->lpVtbl;
        LODWORD(v10) = 0;
        v6 = ((__int64 (__fastcall *)(struct IStream *, unsigned __int16 *, _QWORD, __int64 *))v9->Read)(
               a1,
               v4,
               (unsigned int)(2 * v7),
               &v10);
        if ( (unsigned int)v10 != 2 * v7 )
          v6 = -2147418113;
        v4[v7] = 0;
        if ( v6 >= 0 )
        {
          *a2 = v4;
          return (unsigned int)v6;
        }
      }
      else
      {
        v6 = -2147024882;
      }
    }
  }
  *a2 = 0;
  CoTaskMemFree(v4);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800fe318  mov     r11, rsp
0x1800fe31b  mov     [r11+10h], rbx
0x1800fe31f  mov     [r11+20h], rsi
0x1800fe323  push    rdi
0x1800fe324  push    r14
0x1800fe326  push    r15
0x1800fe328  sub     rsp, 30h
0x1800fe32c  mov     rax, [rcx]
0x1800fe32f  lea     r9, [r11+18h]
0x1800fe333  mov     r15, rdx
0x1800fe336  mov     qword ptr [r11+8], 0
0x1800fe33e  mov     rdx, [r11+8]
0x1800fe342  xor     edi, edi
0x1800fe344  mov     r14, rcx
0x1800fe347  mov     qword ptr [r11+18h], 0
0x1800fe34f  mov     rax, [rax+28h]
0x1800fe353  lea     r8d, [rdi+2]
0x1800fe357  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fe35c  mov     ebx, eax
0x1800fe35e  test    eax, eax
0x1800fe360  js      short loc_1800FE3A1
0x1800fe362  mov     rax, [r14]
0x1800fe365  xor     r9d, r9d
0x1800fe368  mov     rdx, [rsp+48h+arg_0]
0x1800fe36d  xor     r8d, r8d
0x1800fe370  mov     rcx, r14
0x1800fe373  mov     rax, [rax+28h]
0x1800fe377  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fe37c  mov     ebx, eax
0x1800fe37e  test    eax, eax
0x1800fe380  js      short loc_1800FE3A1
0x1800fe382  mov     esi, dword ptr [rsp+48h+arg_10]
0x1800fe386  shr     esi, 1
0x1800fe388  lea     ecx, [rsi+1]
0x1800fe38b  add     rcx, rcx; cb
0x1800fe38e  call    cs:__imp_CoTaskMemAlloc
0x1800fe394  mov     rdi, rax
0x1800fe397  test    rax, rax
0x1800fe39a  jnz     short loc_1800FE3C7
0x1800fe39c  mov     ebx, 8007000Eh
0x1800fe3a1  mov     rcx, rdi; pv
0x1800fe3a4  mov     qword ptr [r15], 0
0x1800fe3ab  call    cs:__imp_CoTaskMemFree
0x1800fe3b1  mov     rsi, [rsp+48h+arg_18]
0x1800fe3b6  mov     eax, ebx
0x1800fe3b8  mov     rbx, [rsp+48h+arg_8]
0x1800fe3bd  add     rsp, 30h
0x1800fe3c1  pop     r15
0x1800fe3c3  pop     r14
0x1800fe3c5  pop     rdi
0x1800fe3c6  retn
0x1800fe3c7  mov     rax, [r14]
0x1800fe3ca  lea     r8d, [rsi+rsi]
0x1800fe3ce  lea     r9, [rsp+48h+arg_0]
0x1800fe3d3  mov     dword ptr [rsp+48h+arg_0], 0
0x1800fe3db  mov     rdx, rdi
0x1800fe3de  mov     rcx, r14
0x1800fe3e1  mov     rax, [rax+18h]
0x1800fe3e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fe3ea  mov     ebx, eax
0x1800fe3ec  lea     rcx, [rsi+rsi]
0x1800fe3f0  mov     eax, dword ptr [rsp+48h+arg_0]
0x1800fe3f4  mov     edx, 8000FFFFh
0x1800fe3f9  cmp     rax, rcx
0x1800fe3fc  cmovnz  ebx, edx
0x1800fe3ff  xor     eax, eax
0x1800fe401  mov     [rcx+rdi], ax
0x1800fe405  test    ebx, ebx
0x1800fe407  js      short loc_1800FE3A1
0x1800fe409  mov     [r15], rdi
0x1800fe40c  jmp     short loc_1800FE3B1
```
