# DescriptorAllocator<SOS_ParentBlockDescriptor,0>::InstallPartialPageAsActive(DescriptorAllocator<SOS_ParentBlockDescriptor,0>::PageDesc *,uint,ushort,bool)

- ea: `0x100437e40`
- end: `0x100437e9b`
- name: `?InstallPartialPageAsActive@?$DescriptorAllocator@VSOS_ParentBlockDescriptor@@$0A@@@AEAA_NPEAUPageDesc@1@IG_N@Z`
- size: `91`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x100416970`

## callees

- `0x100437e40`

## import_xrefs

- `KERNEL32!InterlockedPushEntrySList` at `0x10049c26c`
- `KERNEL32!InterlockedPushEntrySList` at `0x10049c2cd`
- `KERNEL32!InterlockedPushEntrySList` at `0x10049c26c`
- `KERNEL32!InterlockedPushEntrySList` at `0x10049c2cd`
- `KERNEL32!InterlockedPopEntrySList` at `0x100437ed4`
- `KERNEL32!InterlockedPopEntrySList` at `0x10049c277`
- `KERNEL32!InterlockedPopEntrySList` at `0x100437ed4`
- `KERNEL32!InterlockedPopEntrySList` at `0x10049c277`

## pseudocode

```c
bool __fastcall DescriptorAllocator<SOS_ParentBlockDescriptor,0>::InstallPartialPageAsActive(
        __int64 a1,
        signed __int64 a2,
        unsigned int a3,
        unsigned __int16 a4,
        char a5)
{
  __int64 v5; // rcx
  __int64 v6; // rax
  unsigned int v7; // r8d
  struct _SLIST_ENTRY *v8; // rdx
  signed __int64 v10; // rbx
  unsigned __int16 v11; // r15
  unsigned __int64 v13; // r12
  __int64 v14; // r14
  int v15; // esi
  PSLIST_ENTRY v16; // rax
  bool v17; // zf
  PSLIST_ENTRY v19; // rax
  signed __int32 v20[22]; // [rsp+0h] [rbp-58h] BYREF
  unsigned __int16 v21; // [rsp+70h] [rbp+18h]
  unsigned __int16 v22; // [rsp+78h] [rbp+20h]

  v10 = 0;
  v11 = a4;
  v21 = a4;
  v13 = *(_QWORD *)(a1 + 1216) + ((unsigned __int64)a3 << *(_BYTE *)(a1 + 1228));
  v22 = a4;
  if ( !a5 )
  {
    if ( a4 + 1 != *(_WORD *)(a1 + 8) )
      JUMPOUT(0x100437E9BLL);
    v22 = 0;
  }
  while ( 2 )
  {
    v14 = 192LL * v11 + a1 + 1280;
    v15 = 0;
    while ( (unsigned int)v15 < 5 )
    {
      v10 = 0;
      v16 = InterlockedPopEntrySList((PSLIST_HEADER)(v14 + 16LL * v15));
      if ( v16 )
        v10 = (signed __int64)&v16[-1];
      if ( !v10 )
        goto LABEL_16;
      while ( 1 )
      {
        v5 = *(_DWORD *)(v10 + 40) / 0xEu;
        if ( (int)v5 <= v15 )
          break;
        _mm_lfence();
        InterlockedPushEntrySList((PSLIST_HEADER)(v14 + 16 * v5), (PSLIST_ENTRY)(v10 + 16));
        v10 = 0;
        v19 = InterlockedPopEntrySList((PSLIST_HEADER)(v14 + 16LL * v15));
        if ( v19 )
          v10 = (signed __int64)&v19[-1];
        if ( !v10 )
          goto LABEL_16;
      }
      *(_DWORD *)(v10 + 48) = 0;
      if ( a2 != _InterlockedCompareExchange64((volatile signed __int64 *)(v13 + 8), v10, a2) )
      {
        *(_DWORD *)(v10 + 48) = 2;
        v6 = *(unsigned __int16 *)(v10 + 44);
        v7 = ((613566757 * (unsigned __int64)*(unsigned int *)(v10 + 40)) >> 32)
           + ((unsigned int)(*(_DWORD *)(v10 + 40) - ((613566757 * (unsigned __int64)*(unsigned int *)(v10 + 40)) >> 32)) >> 1);
        v8 = (struct _SLIST_ENTRY *)(v10 + 16);
LABEL_29:
        InterlockedPushEntrySList((PSLIST_HEADER)(a1 + 16 * ((v7 >> 3) + 4 * (v6 + 2 * (v6 + 10)))), v8);
        goto LABEL_16;
      }
      if ( a2 )
      {
        if ( *(_DWORD *)(a2 + 40) )
        {
          *(_DWORD *)(a2 + 48) = 2;
        }
        else
        {
          *(_DWORD *)(a2 + 48) = 1;
          _InterlockedOr(v20, 0);
          if ( !*(_DWORD *)(a2 + 40) || _InterlockedCompareExchange((volatile signed __int32 *)(a2 + 48), 2, 1) != 1 )
            goto LABEL_16;
        }
        v6 = *(unsigned __int16 *)(a2 + 44);
        v7 = ((613566757 * (unsigned __int64)*(unsigned int *)(a2 + 40)) >> 32)
           + ((unsigned int)(*(_DWORD *)(a2 + 40) - ((613566757 * (unsigned __int64)*(unsigned int *)(a2 + 40)) >> 32)) >> 1);
        v8 = (struct _SLIST_ENTRY *)(a2 + 16);
        goto LABEL_29;
      }
LABEL_16:
      ++v15;
      if ( v10 )
        break;
    }
    v11 = 0;
    if ( v21 + 1 != *(_WORD *)(a1 + 8) )
      v11 = v21 + 1;
    v21 = v11;
    v17 = v10 == 0;
    if ( !v10 )
    {
      if ( v11 == v22 )
      {
        v17 = 1;
        return !v17;
      }
      continue;
    }
    return !v17;
  }
}

```

## disassembly

```asm
0x100437e40  mov     [rsp+arg_0], rbx
0x100437e45  push    rbp
0x100437e46  push    rsi
0x100437e47  push    rdi
0x100437e48  push    r12
0x100437e4a  push    r13
0x100437e4c  push    r14
0x100437e4e  push    r15
0x100437e50  sub     rsp, 20h
0x100437e54  mov     r13, rcx
0x100437e57  mov     r12d, r8d
0x100437e5a  movzx   ecx, byte ptr [rcx+4CCh]
0x100437e61  xor     ebx, ebx
0x100437e63  shl     r12, cl
0x100437e66  movzx   r15d, r9w
0x100437e6a  mov     [rsp+58h+arg_10], r15d
0x100437e6f  mov     rdi, rdx
0x100437e72  add     r12, [r13+4C0h]
0x100437e79  mov     word ptr [rsp+58h+arg_18], r9w
0x100437e7f  cmp     [rsp+58h+arg_20], bl
0x100437e86  jnz     short loc_100437EA0
0x100437e88  lea     eax, [r15+1]
0x100437e8c  mov     [rsp+58h+arg_18], eax
0x100437e90  cmp     ax, [r13+8]
0x100437e95  jz      loc_100438189
0x100422d75  lea     rbx, [rax-10h]
0x100422d79  jmp     loc_100437EE3
0x100422d7f  mov     ecx, [rbx+28h]
0x100422d82  mov     eax, 24924925h
0x100422d87  mul     ecx
0x100422d89  sub     ecx, edx
0x100422d8b  shr     ecx, 1
0x100422d8d  add     ecx, edx
0x100422d8f  shr     ecx, 3
0x100422d92  cmp     ecx, esi
0x100422d94  jg      loc_10049C25E
0x100422d9a  mov     dword ptr [rbx+30h], 0
0x100422da1  mov     rax, rdi
0x100422da4  lock cmpxchg [r12+8], rbx
0x100422dab  jnz     loc_10049C295
0x100422db1  test    rdi, rdi
0x100422db4  jz      loc_100437EEC
0x100422dba  mov     eax, [rdi+28h]
0x100422dbd  test    eax, eax
0x100422dbf  jnz     loc_10049C2DA
0x100422dc5  mov     dword ptr [rdi+30h], 1
0x100422dcc  lock or [rsp+58h+var_58], eax
0x100422dd0  mov     eax, [rdi+28h]
0x100422dd3  test    eax, eax
0x100422dd5  jz      loc_100437EEC
0x100422ddb  mov     eax, 1
0x100422de0  lock cmpxchg [rdi+30h], r15d
0x100422de6  jnz     loc_100437EEC
0x100422dec  jmp     short loc_100422DEF
0x100422def  mov     ecx, [rdi+28h]
0x100422df2  mov     eax, 24924925h
0x100422df7  mul     ecx
0x100422df9  movzx   eax, word ptr [rdi+2Ch]
0x100422dfd  sub     ecx, edx
0x100422dff  shr     ecx, 1
0x100422e01  lea     r8d, [rdx+rcx]
0x100422e05  lea     rdx, [rdi+10h]; ListEntry
0x100422e09  jmp     loc_10049C2B6
0x100437ea0  movzx   eax, r15w
0x100437ea4  lea     r14, [r13+500h]
0x100437eab  lea     rcx, [rax+rax*2]
0x100437eaf  shl     rcx, 6
0x100437eb3  add     r14, rcx
0x100437eb6  xor     esi, esi
0x100437eb8  lea     r15d, [rsi+2]
0x100437ebc  nop     dword ptr [rax+00h]
0x100437ec0  cmp     esi, 5
0x100437ec3  jnb     short loc_100437EF3
0x100437ec5  movsxd  rbp, esi
0x100437ec8  xor     ebx, ebx
0x100437eca  shl     rbp, 4
0x100437ece  add     rbp, r14
0x100437ed1  mov     rcx, rbp; ListHead
0x100437ed4  call    cs:__imp_InterlockedPopEntrySList
0x100437eda  test    rax, rax
0x100437edd  jnz     loc_100422D75
0x100437ee3  test    rbx, rbx
0x100437ee6  jnz     loc_100422D7F
0x100437eec  inc     esi
0x100437eee  test    rbx, rbx
0x100437ef1  jz      short loc_100437EC0
0x100437ef3  mov     eax, [rsp+58h+arg_10]
0x100437ef7  xor     r15d, r15d
0x100437efa  inc     ax
0x100437efd  cmp     ax, [r13+8]
0x100437f02  cmovnz  r15w, ax
0x100437f07  mov     [rsp+58h+arg_10], r15d
0x100437f0c  test    rbx, rbx
0x100437f0f  jnz     short loc_100437F1C
0x100437f11  cmp     r15w, word ptr [rsp+58h+arg_18]
0x100437f17  jnz     short loc_100437EA0
0x100437f19  test    rbx, rbx
0x100437f1c  mov     rbx, [rsp+58h+arg_0]
0x100437f21  setnz   al
0x100437f24  add     rsp, 20h
0x100437f28  pop     r15
0x100437f2a  pop     r14
0x100437f2c  pop     r13
0x100437f2e  pop     r12
0x100437f30  pop     rdi
0x100437f31  pop     rsi
0x100437f32  pop     rbp
0x100437f33  retn
0x100438189  mov     [rsp+58h+arg_18], ebx
0x10043818d  jmp     loc_100437EA0
0x10049c25e  lfence
0x10049c261  shl     rcx, 4
0x10049c265  lea     rdx, [rbx+10h]; ListEntry
0x10049c269  add     rcx, r14; ListHead
0x10049c26c  call    cs:__imp_InterlockedPushEntrySList
0x10049c272  mov     rcx, rbp; ListHead
0x10049c275  xor     ebx, ebx
0x10049c277  call    cs:__imp_InterlockedPopEntrySList
0x10049c27d  test    rax, rax
0x10049c280  jz      short loc_10049C286
0x10049c282  lea     rbx, [rax-10h]
0x10049c286  test    rbx, rbx
0x10049c289  jnz     loc_100422D7F
0x10049c28f  jmp     loc_100437EEC
0x10049c295  mov     [rbx+30h], r15d
0x10049c299  mov     eax, 24924925h
0x10049c29e  mov     ecx, [rbx+28h]
0x10049c2a1  mul     ecx
0x10049c2a3  movzx   eax, word ptr [rbx+2Ch]
0x10049c2a7  sub     ecx, edx
0x10049c2a9  shr     ecx, 1
0x10049c2ab  lea     r8d, [rdx+rcx]
0x10049c2af  lea     rdx, [rbx+10h]
0x10049c2b3  jmp     short loc_10049C2B6
0x10049c2b6  shr     r8d, 3
0x10049c2ba  lea     rcx, [rax+0Ah]
0x10049c2be  lea     rcx, [rax+rcx*2]
0x10049c2c2  lea     rcx, [r8+rcx*4]
0x10049c2c6  shl     rcx, 4
0x10049c2ca  add     rcx, r13; ListHead
0x10049c2cd  call    cs:__imp_InterlockedPushEntrySList
0x10049c2d3  nop
0x10049c2d4  jmp     loc_100437EEC
0x10049c2da  mov     [rdi+30h], r15d
0x10049c2de  jmp     loc_100422DEF
```
