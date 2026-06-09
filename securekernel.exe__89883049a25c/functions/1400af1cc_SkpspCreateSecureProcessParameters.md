# SkpspCreateSecureProcessParameters

- ea: `0x1400af1cc`
- end: `0x1400af51f`
- name: `SkpspCreateSecureProcessParameters`
- size: `851`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: ``

## callers

- `0x1400aeeec`

## callees

- `0x14000f0f0`
- `0x14001e53c`
- `0x14002ba08`
- `0x1400aed8c`
- `0x1400aee6c`
- `0x1400af1cc`
- `0x1400af7f8`
- `0x1400d4e8c`
- `0x1400ef620`
- `0x1400fc6dc`
- `0x1400fc718`
- `0x1400fc7c0`
- `0x1400fc808`
- `0x1400fc84c`

## pseudocode

```c
__int64 __fastcall SkpspCreateSecureProcessParameters(__int64 a1, PVOID *a2)
{
  int v3; // eax
  NTSTATUS v4; // ebx
  __int64 v5; // r14
  __int64 v6; // r15
  char *v7; // rsi
  char *v8; // rbx
  char *v9; // rbx
  int v10; // eax
  unsigned __int64 v11; // rax
  unsigned __int64 i; // rbx
  __int16 UShortFromUser; // ax
  char *v14; // rsi
  ULONG_PTR v15; // rcx
  _WORD *v16; // rax
  PVOID BaseAddress; // [rsp+30h] [rbp-88h] BYREF
  ULONG_PTR RegionSize; // [rsp+38h] [rbp-80h] BYREF
  __int64 v20; // [rsp+40h] [rbp-78h] BYREF
  __int64 v21; // [rsp+48h] [rbp-70h] BYREF
  char *v22; // [rsp+50h] [rbp-68h]
  __int128 v23; // [rsp+58h] [rbp-60h] BYREF
  char *v24; // [rsp+68h] [rbp-50h]
  unsigned __int64 v25; // [rsp+70h] [rbp-48h]
  __int128 v26[4]; // [rsp+78h] [rbp-40h] BYREF
  unsigned int v28; // [rsp+D8h] [rbp+20h]
  char *v29; // [rsp+D8h] [rbp+20h]

  v26[0] = 0;
  v23 = 0;
  RegionSize = 0;
  v20 = 0;
  v21 = 0;
  BaseAddress = 0;
  v3 = SkpspMapNormalProcessParameters(&v20, &v21);
  v4 = v3;
  if ( v3 < 0 )
  {
    DbgPrint("SkpspMapNormalProcessParameters failed with error 0x%x\n", v3);
    v5 = v20;
    v6 = v21;
  }
  else
  {
    v5 = v20;
    v6 = v21;
    v4 = SkpspCaptureUnicodeStringParameter(v20 + 112, v26, v20, v21);
    if ( v4 >= 0 )
    {
      v4 = SkpspCaptureUnicodeStringParameter(v5 + 96, &v23, v5, v6);
      if ( v4 >= 0 )
      {
        v7 = 0;
        v28 = (unsigned __int16)v23 + 1112 + LOWORD(v26[0]);
        BaseAddress = 0;
        v22 = (char *)v28;
        RegionSize = v28;
        v4 = ZwAllocateVirtualMemory((HANDLE)0xFFFFFFFFFFFFFFFFLL, &BaseAddress, 0, &RegionSize, 0x1000u, 4u);
        if ( v4 >= 0 )
        {
          RtlSetUserMemory(BaseAddress);
          RtlWriteULongToUser((_DWORD *)BaseAddress + 2, -2147467263);
          RtlWriteULongToUser((_DWORD *)BaseAddress + 259, 1);
          RtlWriteULongToUser((_DWORD *)BaseAddress + 1, v28);
          RtlWriteULongToUser(BaseAddress, v28);
          RtlWriteUShortToUser((char *)BaseAddress + 58, 520);
          v8 = (char *)BaseAddress + 1104;
          v9 = &v8[(unsigned int)SkpspCopyUnicodeString((char *)BaseAddress + 1104)];
          v29 = v9;
          v10 = SkpspCopyUnicodeString(v9);
          RtlWriteULong64ToUser((_QWORD *)BaseAddress + 16, (__int64)&v9[v10]);
          RtlWriteULong64ToUser((_QWORD *)BaseAddress + 126, 4);
          if ( v9 )
          {
            v25 = 0;
            v24 = 0;
            v11 = ((unsigned __int64)(unsigned __int16)v23 + 2) >> 1;
            *(_QWORD *)&v26[0] = v11;
            for ( i = 0; ; ++i )
            {
              v25 = i;
              if ( i >= v11 )
                break;
              v22 = &v29[2 * i];
              UShortFromUser = RtlReadUShortFromUser(v22);
              if ( !UShortFromUser )
                break;
              if ( UShortFromUser == 92 )
                v7 = v22;
              v24 = v7;
              v11 = *(_QWORD *)&v26[0];
            }
            v9 = v29;
          }
          if ( v7 )
          {
            v14 = v7 + 2;
            RegionSize = 2 * ((v14 - v29) >> 1);
            v15 = (unsigned __int16)v23 - RegionSize;
          }
          else
          {
            v15 = (unsigned __int16)v23;
            v14 = v9;
          }
          RegionSize = v15;
          if ( v15 )
          {
            *(_QWORD *)(a1 + 352) = SkAllocatePool(512, v15 + 18);
            LOWORD(v15) = RegionSize;
          }
          v16 = *(_WORD **)(a1 + 352);
          if ( v16 )
          {
            *v16 = v15;
            *(_WORD *)(*(_QWORD *)(a1 + 352) + 2LL) = RegionSize + 2;
            *(_QWORD *)(*(_QWORD *)(a1 + 352) + 8LL) = *(_QWORD *)(a1 + 352) + 16LL;
            RtlCopyFromUser(*(void **)(*(_QWORD *)(a1 + 352) + 8LL), v14, RegionSize);
          }
          *a2 = BaseAddress;
          v4 = 0;
        }
      }
    }
  }
  if ( v5 )
    SkmmReleaseTemporaryView(v5, v6);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1400af1cc  mov     rax, rsp
0x1400af1cf  mov     [rax+8], rbx
0x1400af1d3  mov     [rax+10h], rdx
0x1400af1d7  push    rsi
0x1400af1d8  push    rdi
0x1400af1d9  push    r13
0x1400af1db  push    r14
0x1400af1dd  push    r15
0x1400af1df  sub     rsp, 90h
0x1400af1e6  mov     r13, rcx
0x1400af1e9  xorps   xmm0, xmm0
0x1400af1ec  movups  xmmword ptr [rax-40h], xmm0
0x1400af1f0  xorps   xmm1, xmm1
0x1400af1f3  movups  xmmword ptr [rax-60h], xmm1
0x1400af1f7  xor     edi, edi
0x1400af1f9  mov     [rax-80h], rdi
0x1400af1fd  mov     [rax-78h], rdi
0x1400af201  mov     [rax-70h], rdi
0x1400af205  mov     [rsp+0B8h+BaseAddress], rdi
0x1400af20a  lea     rdx, [rax-70h]
0x1400af20e  lea     rcx, [rax-78h]
0x1400af212  call    SkpspMapNormalProcessParameters
0x1400af217  mov     ebx, eax
0x1400af219  test    eax, eax
0x1400af21b  js      loc_1400AF4DC
0x1400af221  mov     r14, [rsp+0B8h+var_78]
0x1400af226  lea     rcx, [r14+70h]
0x1400af22a  mov     r15, [rsp+0B8h+var_70]
0x1400af22f  mov     r9, r15
0x1400af232  mov     r8, r14
0x1400af235  lea     rdx, [rsp+0B8h+var_40]
0x1400af23a  call    SkpspCaptureUnicodeStringParameter
0x1400af23f  mov     ebx, eax
0x1400af241  test    eax, eax
0x1400af243  js      loc_1400AF4F4
0x1400af249  lea     rcx, [r14+60h]
0x1400af24d  mov     r9, r15
0x1400af250  mov     r8, r14
0x1400af253  lea     rdx, [rsp+0B8h+var_60]
0x1400af258  call    SkpspCaptureUnicodeStringParameter
0x1400af25d  mov     ebx, eax
0x1400af25f  test    eax, eax
0x1400af261  js      loc_1400AF4F4
0x1400af267  mov     esi, edi
0x1400af269  movzx   ecx, word ptr [rsp+0B8h+var_60]
0x1400af26e  movzx   eax, word ptr [rsp+0B8h+var_40]
0x1400af273  add     ecx, 458h
0x1400af279  add     eax, ecx
0x1400af27b  mov     dword ptr [rsp+0B8h+arg_18], eax
0x1400af282  mov     [rsp+0B8h+BaseAddress], rdi
0x1400af287  mov     [rsp+0B8h+var_68], rax
0x1400af28c  mov     [rsp+0B8h+RegionSize], rax
0x1400af291  mov     [rsp+0B8h+Protect], 4; Protect
0x1400af299  mov     [rsp+0B8h+AllocationType], 1000h; AllocationType
0x1400af2a1  lea     r9, [rsp+0B8h+RegionSize]; RegionSize
0x1400af2a6  xor     r8d, r8d; ZeroBits
0x1400af2a9  lea     rdx, [rsp+0B8h+BaseAddress]; BaseAddress
0x1400af2ae  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x1400af2b2  call    ZwAllocateVirtualMemory
0x1400af2b7  mov     ebx, eax
0x1400af2b9  test    eax, eax
0x1400af2bb  js      loc_1400AF4F4
0x1400af2c1  mov     r8, [rsp+0B8h+var_68]
0x1400af2c6  xor     edx, edx
0x1400af2c8  mov     rcx, [rsp+0B8h+BaseAddress]; void *
0x1400af2cd  call    RtlSetUserMemory
0x1400af2d2  mov     rcx, [rsp+0B8h+BaseAddress]
0x1400af2d7  add     rcx, 8
0x1400af2db  mov     edx, 80004001h
0x1400af2e0  call    RtlWriteULongToUser
0x1400af2e5  mov     rcx, [rsp+0B8h+BaseAddress]
0x1400af2ea  add     rcx, 40Ch
0x1400af2f1  lea     edx, [rdi+1]
0x1400af2f4  call    RtlWriteULongToUser
0x1400af2f9  mov     rcx, [rsp+0B8h+BaseAddress]
0x1400af2fe  add     rcx, 4
0x1400af302  mov     edx, dword ptr [rsp+0B8h+arg_18]
0x1400af309  call    RtlWriteULongToUser
0x1400af30e  mov     edx, dword ptr [rsp+0B8h+arg_18]
0x1400af315  mov     rcx, [rsp+0B8h+BaseAddress]
0x1400af31a  call    RtlWriteULongToUser
0x1400af31f  mov     edx, 208h
0x1400af324  mov     rcx, [rsp+0B8h+BaseAddress]
0x1400af329  add     rcx, 3Ah ; ':'
0x1400af32d  call    RtlWriteUShortToUser
0x1400af332  mov     rdx, [rsp+0B8h+BaseAddress]
0x1400af337  lea     rbx, [rdx+450h]
0x1400af33e  add     rdx, 70h ; 'p'
0x1400af342  lea     r8, [rsp+0B8h+var_40]
0x1400af347  mov     rcx, rbx; void *
0x1400af34a  call    SkpspCopyUnicodeString
0x1400af34f  mov     eax, eax
0x1400af351  add     rbx, rax
0x1400af354  mov     [rsp+0B8h+arg_18], rbx
0x1400af35c  mov     rdx, [rsp+0B8h+BaseAddress]
0x1400af361  add     rdx, 60h ; '`'
0x1400af365  lea     r8, [rsp+0B8h+var_60]
0x1400af36a  mov     rcx, rbx; void *
0x1400af36d  call    SkpspCopyUnicodeString
0x1400af372  mov     edx, eax
0x1400af374  add     rdx, rbx
0x1400af377  mov     rcx, [rsp+0B8h+BaseAddress]
0x1400af37c  sub     rcx, 0FFFFFFFFFFFFFF80h
0x1400af380  call    RtlWriteULong64ToUser
0x1400af385  mov     rcx, [rsp+0B8h+BaseAddress]
0x1400af38a  add     rcx, 3F0h
0x1400af391  lea     edx, [rdi+4]
0x1400af394  call    RtlWriteULong64ToUser
0x1400af399  test    rbx, rbx
0x1400af39c  jz      short loc_1400AF409
0x1400af39e  movzx   eax, word ptr [rsp+0B8h+var_60]
0x1400af3a3  add     rax, 2
0x1400af3a7  mov     [rsp+0B8h+var_50], rdi
0x1400af3ac  mov     [rsp+0B8h+var_48], rdi
0x1400af3b1  mov     [rsp+0B8h+var_50], rdi
0x1400af3b6  shr     rax, 1
0x1400af3b9  mov     qword ptr [rsp+0B8h+var_40], rax
0x1400af3be  mov     ebx, edi
0x1400af3c0  mov     [rsp+0B8h+var_48], rbx
0x1400af3c5  cmp     rbx, rax
0x1400af3c8  jnb     short loc_1400AF401
0x1400af3ca  mov     rax, [rsp+0B8h+arg_18]
0x1400af3d2  lea     rax, [rax+rbx*2]
0x1400af3d6  mov     [rsp+0B8h+var_68], rax
0x1400af3db  mov     rcx, rax
0x1400af3de  call    RtlReadUShortFromUser
0x1400af3e3  test    ax, ax
0x1400af3e6  jz      short loc_1400AF401
0x1400af3e8  cmp     ax, 5Ch ; '\'
0x1400af3ec  cmovz   rsi, [rsp+0B8h+var_68]
0x1400af3f2  mov     [rsp+0B8h+var_50], rsi
0x1400af3f7  inc     rbx
0x1400af3fa  mov     rax, qword ptr [rsp+0B8h+var_40]
0x1400af3ff  jmp     short loc_1400AF3C0
0x1400af401  mov     rbx, [rsp+0B8h+arg_18]
0x1400af409  test    rsi, rsi
0x1400af40c  jz      short loc_1400AF436
0x1400af40e  mov     ebx, 2
0x1400af413  add     rsi, rbx
0x1400af416  mov     rax, rsi
0x1400af419  sub     rax, [rsp+0B8h+arg_18]
0x1400af421  sar     rax, 1
0x1400af424  add     rax, rax
0x1400af427  mov     [rsp+0B8h+RegionSize], rax
0x1400af42c  movzx   ecx, word ptr [rsp+0B8h+var_60]
0x1400af431  sub     rcx, rax
0x1400af434  jmp     short loc_1400AF443
0x1400af436  movzx   ecx, word ptr [rsp+0B8h+var_60]
0x1400af43b  mov     rsi, rbx
0x1400af43e  mov     ebx, 2
0x1400af443  mov     rdx, rcx
0x1400af446  mov     [rsp+0B8h+RegionSize], rcx
0x1400af44b  test    rcx, rcx
0x1400af44e  jz      short loc_1400AF470
0x1400af450  add     rdx, 12h
0x1400af454  mov     ecx, 200h
0x1400af459  mov     r8d, 73706B53h
0x1400af45f  call    SkAllocatePool
0x1400af464  mov     [r13+160h], rax
0x1400af46b  mov     rcx, [rsp+0B8h+RegionSize]
0x1400af470  mov     rax, [r13+160h]
0x1400af477  test    rax, rax
0x1400af47a  jz      short loc_1400AF4BA
0x1400af47c  mov     [rax], cx
0x1400af47f  movzx   ecx, word ptr [rsp+0B8h+RegionSize]
0x1400af484  add     cx, bx
0x1400af487  mov     rax, [r13+160h]
0x1400af48e  mov     [rax+2], cx
0x1400af492  mov     rcx, [r13+160h]
0x1400af499  lea     rax, [rcx+10h]
0x1400af49d  mov     [rcx+8], rax
0x1400af4a1  mov     rcx, [r13+160h]
0x1400af4a8  mov     r8, [rsp+0B8h+RegionSize]; Size
0x1400af4ad  mov     rdx, rsi; Src
0x1400af4b0  mov     rcx, [rcx+8]; void *
0x1400af4b4  call    RtlCopyFromUser
0x1400af4b9  nop
0x1400af4ba  mov     rax, [rsp+0B8h+BaseAddress]
0x1400af4bf  mov     rcx, [rsp+0B8h+arg_8]
0x1400af4c7  mov     [rcx], rax
0x1400af4ca  mov     ebx, edi
0x1400af4cc  jmp     short loc_1400AF4F4
0x1400af4ce  mov     ebx, eax
0x1400af4d0  mov     r14, [rsp+0B8h+var_78]
0x1400af4d5  mov     r15, [rsp+0B8h+var_70]
0x1400af4da  jmp     short loc_1400AF4F4
0x1400af4dc  mov     edx, eax
0x1400af4de  lea     rcx, aSkpspmapnormal; "SkpspMapNormalProcessParameters failed "...
0x1400af4e5  call    DbgPrint
0x1400af4ea  mov     r14, [rsp+0B8h+var_78]
0x1400af4ef  mov     r15, [rsp+0B8h+var_70]
0x1400af4f4  test    r14, r14
0x1400af4f7  jz      short loc_1400AF504
0x1400af4f9  mov     rdx, r15
0x1400af4fc  mov     rcx, r14
0x1400af4ff  call    SkmmReleaseTemporaryView
0x1400af504  mov     eax, ebx
0x1400af506  mov     rbx, [rsp+0B8h+arg_0]
0x1400af50e  add     rsp, 90h
0x1400af515  pop     r15
0x1400af517  pop     r14
0x1400af519  pop     r13
0x1400af51b  pop     rdi
0x1400af51c  pop     rsi
0x1400af51d  retn
```
