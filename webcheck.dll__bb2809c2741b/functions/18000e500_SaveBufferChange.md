# SaveBufferChange

- ea: `0x18000e500`
- end: `0x18000e680`
- name: `SaveBufferChange`
- size: `384`
- prototype: `__int64 __fastcall(struct OOEBuf *, int)`
- caller_count: `5`
- callee_count: `7`
- tags: `service_task, installer_update`

## callers

- `0x180005390`
- `0x18000ad80`
- `0x1800121f0`
- `0x180013490`
- `0x180014850`

## callees

- `0x18000c740`
- `0x18000e3c4`
- `0x18000e500`
- `0x18001c054`
- `0x18001c384`
- `0x18001d420`
- `0x18002924e`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x18000e556`
- `ole32!CoTaskMemAlloc` at `0x18000e623`
- `ole32!CoTaskMemAlloc` at `0x18000e556`
- `ole32!CoTaskMemAlloc` at `0x18000e623`
- `ole32!CoTaskMemFree` at `0x18000e5f7`
- `ole32!CoTaskMemFree` at `0x18000e663`
- `ole32!CoTaskMemFree` at `0x18000e5f7`
- `ole32!CoTaskMemFree` at `0x18000e663`

## pseudocode

```c
__int64 __fastcall SaveBufferChange(struct OOEBuf *a1, int a2)
{
  unsigned int v5; // eax
  unsigned __int16 v6; // bx
  char *v7; // rax
  struct _GUID *v8; // rdi
  int v9; // r14d
  int v10; // ebx
  const WCHAR *v11; // rcx
  unsigned __int16 v12; // bx
  char *v13; // rax
  struct _GUID v14; // [rsp+20h] [rbp-48h] BYREF
  unsigned int v15; // [rsp+70h] [rbp+8h] BYREF

  if ( !*(_DWORD *)a1 )
    return 0;
  v5 = BufferSize();
  v15 = v5;
  if ( v5 <= 0xFFFF )
  {
    v6 = v5 + 224;
    if ( (unsigned __int16)(v5 + 224) >= (unsigned __int16)v5 && (unsigned __int64)v6 + 2 >= v6 )
    {
      v7 = (char *)CoTaskMemAlloc(v6 + 2LL);
      v8 = (struct _GUID *)v7;
      if ( v7 )
      {
        memset_0(v7, 0, v6 + 2LL);
        LOWORD(v8->Data1) = v6;
        HIWORD(v8->Data1) = 29701;
        CopyToMyPooe(a1, v8->Data4);
        *(_DWORD *)a1 = 0;
        v9 = PersistUpdate((struct OOEntry *)v8->Data4, a2);
        if ( v9 < 0 )
        {
LABEL_15:
          CoTaskMemFree(v8);
          return (unsigned int)v9;
        }
        v10 = *((_DWORD *)a1 + 1376);
        v11 = (const WCHAR *)&v8->Data4[*(_QWORD *)v8[12].Data4];
        v14 = v8[8];
        v9 = LoadWithCookie(v11, a1, &v15, &v14);
        v8[8] = v14;
        *((_DWORD *)a1 + 1376) = v10;
        *(_DWORD *)a1 = 0;
        if ( v9 )
        {
LABEL_14:
          GenerateEvent(0x2000, (LPCITEMIDLIST)v8);
          goto LABEL_15;
        }
        CoTaskMemFree(v8);
        if ( v15 <= 0xFFFF )
        {
          v12 = v15 + 224;
          if ( (unsigned __int16)(v15 + 224) >= (unsigned __int16)v15 && (unsigned __int64)v12 + 2 >= v12 )
          {
            v13 = (char *)CoTaskMemAlloc(v12 + 2LL);
            v8 = (struct _GUID *)v13;
            if ( v13 )
            {
              memset_0(v13, 0, v12 + 2LL);
              LOWORD(v8->Data1) = v12;
              HIWORD(v8->Data1) = 29701;
              CopyToMyPooe(a1, v8->Data4);
              goto LABEL_14;
            }
          }
        }
      }
    }
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x18000e500  push    rbx
0x18000e502  push    rbp
0x18000e503  push    rsi
0x18000e504  push    rdi
0x18000e505  push    r14
0x18000e507  push    r15
0x18000e509  sub     rsp, 38h
0x18000e50d  cmp     dword ptr [rcx], 0
0x18000e510  mov     r14d, edx
0x18000e513  mov     rsi, rcx
0x18000e516  jnz     short loc_18000E51F
0x18000e518  xor     eax, eax
0x18000e51a  jmp     loc_18000E673
0x18000e51f  call    BufferSize
0x18000e524  mov     [rsp+68h+arg_0], eax
0x18000e528  cmp     eax, 0FFFFh
0x18000e52d  ja      loc_18000E66E
0x18000e533  mov     ebx, 0E0h
0x18000e538  add     ebx, eax
0x18000e53a  cmp     bx, ax
0x18000e53d  jb      loc_18000E66E
0x18000e543  movzx   eax, bx
0x18000e546  lea     rbp, [rax+2]
0x18000e54a  cmp     rbp, rax
0x18000e54d  jb      loc_18000E66E
0x18000e553  mov     rcx, rbp; cb
0x18000e556  call    cs:__imp_CoTaskMemAlloc
0x18000e55c  mov     rdi, rax
0x18000e55f  test    rax, rax
0x18000e562  jz      loc_18000E66E
0x18000e568  mov     r8, rbp; Size
0x18000e56b  xor     edx, edx; Val
0x18000e56d  mov     rcx, rax; void *
0x18000e570  call    memset_0
0x18000e575  lea     r15, [rdi+8]
0x18000e579  mov     [rdi], bx
0x18000e57c  mov     rdx, r15
0x18000e57f  mov     word ptr [rdi+2], 7405h
0x18000e585  mov     rcx, rsi
0x18000e588  call    CopyToMyPooe
0x18000e58d  mov     edx, r14d; int
0x18000e590  mov     dword ptr [rsi], 0
0x18000e596  mov     rcx, r15; struct OOEntry *
0x18000e599  call    PersistUpdate
0x18000e59e  mov     r14d, eax
0x18000e5a1  test    eax, eax
0x18000e5a3  js      loc_18000E660
0x18000e5a9  movups  xmm0, xmmword ptr [r15+78h]
0x18000e5ae  mov     rcx, [r15+0C0h]
0x18000e5b5  lea     r9, [rsp+68h+var_48]; struct _GUID *
0x18000e5ba  mov     ebx, [rsi+1580h]
0x18000e5c0  lea     r8, [rsp+68h+arg_0]; unsigned int *
0x18000e5c5  add     rcx, r15; psz2
0x18000e5c8  mov     rdx, rsi; struct OOEBuf *
0x18000e5cb  movdqu  xmmword ptr [rsp+68h+var_48.Data1], xmm0
0x18000e5d1  call    ?LoadWithCookie@@YAJPEBGPEAUOOEBuf@@PEAKPEAU_GUID@@@Z; LoadWithCookie(ushort const *,OOEBuf *,ulong *,_GUID *)
0x18000e5d6  mov     r14d, eax
0x18000e5d9  movups  xmm0, xmmword ptr [rsp+68h+var_48.Data1]
0x18000e5de  movdqu  xmmword ptr [r15+78h], xmm0
0x18000e5e4  mov     [rsi+1580h], ebx
0x18000e5ea  mov     dword ptr [rsi], 0
0x18000e5f0  test    eax, eax
0x18000e5f2  jnz     short loc_18000E653
0x18000e5f4  mov     rcx, rdi; pv
0x18000e5f7  call    cs:__imp_CoTaskMemFree
0x18000e5fd  mov     eax, [rsp+68h+arg_0]
0x18000e601  cmp     eax, 0FFFFh
0x18000e606  ja      short loc_18000E66E
0x18000e608  mov     ebx, 0E0h
0x18000e60d  add     ebx, eax
0x18000e60f  cmp     bx, ax
0x18000e612  jb      short loc_18000E66E
0x18000e614  movzx   eax, bx
0x18000e617  lea     rbp, [rax+2]
0x18000e61b  cmp     rbp, rax
0x18000e61e  jb      short loc_18000E66E
0x18000e620  mov     rcx, rbp; cb
0x18000e623  call    cs:__imp_CoTaskMemAlloc
0x18000e629  mov     rdi, rax
0x18000e62c  test    rax, rax
0x18000e62f  jz      short loc_18000E66E
0x18000e631  mov     r8, rbp; Size
0x18000e634  xor     edx, edx; Val
0x18000e636  mov     rcx, rax; void *
0x18000e639  call    memset_0
0x18000e63e  lea     rdx, [rdi+8]
0x18000e642  mov     [rdi], bx
0x18000e645  mov     rcx, rsi
0x18000e648  mov     word ptr [rdi+2], 7405h
0x18000e64e  call    CopyToMyPooe
0x18000e653  mov     rdx, rdi; pidl2
0x18000e656  mov     ecx, 2000h; wEventId
0x18000e65b  call    _GenerateEvent
0x18000e660  mov     rcx, rdi; pv
0x18000e663  call    cs:__imp_CoTaskMemFree
0x18000e669  mov     eax, r14d
0x18000e66c  jmp     short loc_18000E673
0x18000e66e  mov     eax, 8007000Eh
0x18000e673  add     rsp, 38h
0x18000e677  pop     r15
0x18000e679  pop     r14
0x18000e67b  pop     rdi
0x18000e67c  pop     rsi
0x18000e67d  pop     rbp
0x18000e67e  pop     rbx
0x18000e67f  retn
```
