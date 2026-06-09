# TextToBlob2(ushort const *,uint,tagBLOB *)

- ea: `0x18002fc50`
- end: `0x18002fcec`
- name: `?TextToBlob2@@YAJPEBGIPEAUtagBLOB@@@Z`
- size: `156`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int, struct tagBLOB *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800340e8`

## callees

- `0x18000a47c`
- `0x18002e070`
- `0x18002fc50`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002fcce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002fcce`

## pseudocode

```c
__int64 __fastcall TextToBlob2(unsigned __int16 *a1, int a2, struct tagBLOB *a3)
{
  ULONG v4; // esi
  unsigned __int16 *v5; // rdi
  int v6; // r10d
  BYTE *v7; // r9
  ULONG v8; // ebp
  char v9; // al
  _BYTE *v10; // r9
  char v11; // al
  char v12; // r11
  void *v14; // [rsp+68h] [rbp+20h] BYREF

  v14 = 0;
  v4 = (unsigned int)(a2 - 2) >> 1;
  v5 = a1;
  v6 = CTCoAllocPolicy::Alloc(a1, 1, v4, &v14);
  if ( v6 < 0 )
    goto LABEL_6;
  v7 = (BYTE *)v14;
  v8 = 0;
  a3->cbSize = v4;
  for ( a3->pBlobData = v7; v8 < v4; ++v8 )
  {
    v9 = CharsToByte(*v5, v5[1]);
    *v10 = v9;
    v5 += 2;
  }
  v11 = CharsToByte(*v5, v5[1]);
  if ( v12 != v11 )
  {
    CoTaskMemFree(a3->pBlobData);
    v6 = -2147024883;
LABEL_6:
    *a3 = 0;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18002fc50  push    rbx
0x18002fc52  push    rbp
0x18002fc53  push    rsi
0x18002fc54  push    rdi
0x18002fc55  sub     rsp, 28h
0x18002fc59  lea     esi, [rdx-2]
0x18002fc5c  mov     [rsp+48h+arg_18], 0
0x18002fc65  mov     rbx, r8
0x18002fc68  shr     esi, 1
0x18002fc6a  mov     r8d, esi; unsigned __int64
0x18002fc6d  lea     r9, [rsp+48h+arg_18]; void **
0x18002fc72  mov     edx, 1; unsigned int
0x18002fc77  mov     rdi, rcx
0x18002fc7a  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x18002fc7f  mov     r10d, eax
0x18002fc82  test    eax, eax
0x18002fc84  js      short loc_18002FCDA
0x18002fc86  mov     r9, [rsp+48h+arg_18]
0x18002fc8b  xor     r11b, r11b
0x18002fc8e  xor     ebp, ebp
0x18002fc90  mov     [rbx], esi
0x18002fc92  mov     [rbx+8], r9
0x18002fc96  test    esi, esi
0x18002fc98  jz      short loc_18002FCB9
0x18002fc9a  movzx   edx, word ptr [rdi+2]
0x18002fc9e  movzx   ecx, word ptr [rdi]
0x18002fca1  call    CharsToByte
0x18002fca6  mov     [r9], al
0x18002fca9  add     rdi, 4
0x18002fcad  inc     r9
0x18002fcb0  add     r11b, al
0x18002fcb3  inc     ebp
0x18002fcb5  cmp     ebp, esi
0x18002fcb7  jb      short loc_18002FC9A
0x18002fcb9  movzx   edx, word ptr [rdi+2]
0x18002fcbd  movzx   ecx, word ptr [rdi]
0x18002fcc0  call    CharsToByte
0x18002fcc5  cmp     r11b, al
0x18002fcc8  jz      short loc_18002FCE0
0x18002fcca  mov     rcx, [rbx+8]; pv
0x18002fcce  call    cs:__imp_CoTaskMemFree
0x18002fcd4  mov     r10d, 8007000Dh
0x18002fcda  xorps   xmm0, xmm0
0x18002fcdd  movups  xmmword ptr [rbx], xmm0
0x18002fce0  mov     eax, r10d
0x18002fce3  add     rsp, 28h
0x18002fce7  pop     rdi
0x18002fce8  pop     rsi
0x18002fce9  pop     rbp
0x18002fcea  pop     rbx
0x18002fceb  retn
```
