# RtlpHpLfhPrivateSlotCreate

- ea: `0x1400cee14`
- end: `0x1400cefce`
- name: `RtlpHpLfhPrivateSlotCreate`
- size: `442`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x14000ffec`

## callees

- `0x1400326d4`
- `0x140032970`
- `0x1400ce76c`
- `0x1400ce82c`
- `0x1400ce94c`
- `0x1400cee14`

## pseudocode

```c
__int64 __fastcall RtlpHpLfhPrivateSlotCreate(__int64 a1, __int64 a2, unsigned __int8 *a3)
{
  __int64 v5; // rdi
  unsigned __int64 v6; // r15
  _OWORD *v7; // rsi
  _OWORD *v8; // r14
  _OWORD *v9; // rax
  __int64 v10; // r8
  __int128 v11; // xmm1
  _WORD *v12; // rdx

  v5 = RtlpHpLfhContextSlotAllocate(a1, a3);
  if ( !v5 )
    return 0;
  LOWORD(v6) = a2;
  v7 = 0;
  v8 = (_OWORD *)(a1 + ((unsigned __int16)a2 << 6));
  if ( (unsigned __int64)v8 < a1 + ((unsigned __int64)*(unsigned __int8 *)(a1 + 64) << 8) + 1472 )
  {
    v9 = (_OWORD *)RtlpHpLfhContextMetadataAllocate(a1, 0);
    v7 = v9;
    v10 = 2;
    if ( !v9 )
    {
      RtlpHpLfhContextMetadataFree(a1, v5, 2);
      return 0;
    }
    do
    {
      *v9 = *v8;
      v9[1] = v8[1];
      v9[2] = v8[2];
      v9[3] = v8[3];
      v9[4] = v8[4];
      v9[5] = v8[5];
      v9[6] = v8[6];
      v11 = v8[7];
      v8 += 8;
      v9[7] = v11;
      v9 += 8;
      --v10;
    }
    while ( v10 );
    v8 = v7;
  }
  *((_WORD *)v8 + ((unsigned __int64)*a3 >> 1)) = (unsigned __int64)(v5 - a1) >> 6;
  if ( v7 )
  {
    v6 = ((unsigned __int64)v7 - a1) >> 6;
    LOWORD(a2) = v6;
    *((_QWORD *)&KeGetPcr()->NtTib.ExceptionList[182].Handler + (unsigned int)(*(_DWORD *)(a1 + 76) - 1)) = a2;
  }
  *(_WORD *)(v5 + 6) = WORD1(a2);
  *(_WORD *)(v5 + 4) = v6;
  *(_DWORD *)(v5 + 20) = *((_DWORD *)KeGetPcr()->NtTib.StackBase + 42);
  RtlpHpAcquireLockExclusive(a3 + 80);
  if ( *((_WORD *)a3 + 45) )
    v12 = (_WORD *)(a1 + (*((unsigned __int16 *)a3 + 45) << 6) + 16LL);
  else
    v12 = a3 + 88;
  *v12 = (unsigned __int64)(v5 - a1) >> 6;
  *(_WORD *)(v5 + 16) = 0;
  *(_WORD *)(v5 + 18) = *((_WORD *)a3 + 45);
  *((_WORD *)a3 + 45) = *v12;
  RtlpHpReleaseLockExclusive(a3 + 80);
  return v5;
}

```

## disassembly

```asm
0x1400cee14  mov     [rsp+arg_8], rdx
0x1400cee19  push    rbx
0x1400cee1a  push    rbp
0x1400cee1b  push    rsi
0x1400cee1c  push    rdi
0x1400cee1d  push    r14
0x1400cee1f  push    r15
0x1400cee21  sub     rsp, 28h
0x1400cee25  mov     rdx, r8
0x1400cee28  mov     rbp, r8
0x1400cee2b  mov     rbx, rcx
0x1400cee2e  call    RtlpHpLfhContextSlotAllocate
0x1400cee33  mov     rdi, rax
0x1400cee36  test    rax, rax
0x1400cee39  jnz     short loc_1400CEE42
0x1400cee3b  xor     edi, edi
0x1400cee3d  jmp     loc_1400CEFBD
0x1400cee42  movzx   r15d, word ptr [rsp+58h+arg_8]
0x1400cee48  xor     esi, esi
0x1400cee4a  movzx   eax, byte ptr [rbx+40h]
0x1400cee4e  mov     r14d, r15d
0x1400cee51  shl     rax, 8
0x1400cee55  shl     r14d, 6
0x1400cee59  add     rax, 5C0h
0x1400cee5f  add     r14, rbx
0x1400cee62  add     rax, rbx
0x1400cee65  cmp     r14, rax
0x1400cee68  jnb     short loc_1400CEEDF
0x1400cee6a  xor     edx, edx
0x1400cee6c  mov     rcx, rbx
0x1400cee6f  call    RtlpHpLfhContextMetadataAllocate
0x1400cee74  mov     rsi, rax
0x1400cee77  mov     r8d, 2
0x1400cee7d  test    rax, rax
0x1400cee80  jz      loc_1400CEF5E
0x1400cee86  lea     ecx, [r8+7Eh]
0x1400cee8a  movups  xmm0, xmmword ptr [r14]
0x1400cee8e  movups  xmmword ptr [rax], xmm0
0x1400cee91  movups  xmm1, xmmword ptr [r14+10h]
0x1400cee96  movups  xmmword ptr [rax+10h], xmm1
0x1400cee9a  movups  xmm0, xmmword ptr [r14+20h]
0x1400cee9f  movups  xmmword ptr [rax+20h], xmm0
0x1400ceea3  movups  xmm1, xmmword ptr [r14+30h]
0x1400ceea8  movups  xmmword ptr [rax+30h], xmm1
0x1400ceeac  movups  xmm0, xmmword ptr [r14+40h]
0x1400ceeb1  movups  xmmword ptr [rax+40h], xmm0
0x1400ceeb5  movups  xmm1, xmmword ptr [r14+50h]
0x1400ceeba  movups  xmmword ptr [rax+50h], xmm1
0x1400ceebe  movups  xmm0, xmmword ptr [r14+60h]
0x1400ceec3  movups  xmmword ptr [rax+60h], xmm0
0x1400ceec7  movups  xmm1, xmmword ptr [r14+70h]
0x1400ceecc  add     r14, rcx
0x1400ceecf  movups  xmmword ptr [rax+70h], xmm1
0x1400ceed3  add     rax, rcx
0x1400ceed6  sub     r8, 1
0x1400ceeda  jnz     short loc_1400CEE8A
0x1400ceedc  mov     r14, rsi
0x1400ceedf  movzx   eax, byte ptr [rbp+0]
0x1400ceee3  mov     rcx, rdi
0x1400ceee6  sub     rcx, rbx
0x1400ceee9  shr     rax, 1
0x1400ceeec  shr     rcx, 6
0x1400ceef0  mov     [r14+rax*2], cx
0x1400ceef5  test    rsi, rsi
0x1400ceef8  jz      short loc_1400CEF27
0x1400ceefa  mov     rdx, gs:0
0x1400cef03  sub     rsi, rbx
0x1400cef06  mov     ecx, [rbx+4Ch]
0x1400cef09  mov     r15, rsi
0x1400cef0c  shr     r15, 6
0x1400cef10  dec     ecx
0x1400cef12  mov     word ptr [rsp+58h+arg_8], r15w
0x1400cef18  xor     esi, esi
0x1400cef1a  mov     rax, [rsp+58h+arg_8]
0x1400cef1f  mov     [rdx+rcx*8+0B68h], rax
0x1400cef27  movzx   eax, word ptr [rsp+58h+arg_8+2]
0x1400cef2c  mov     [rdi+6], ax
0x1400cef30  mov     [rdi+4], r15w
0x1400cef35  mov     rax, gs:8
0x1400cef3e  mov     ecx, [rax+0A8h]
0x1400cef44  mov     [rdi+14h], ecx
0x1400cef47  lea     rcx, [rbp+50h]
0x1400cef4b  call    RtlpHpAcquireLockExclusive
0x1400cef50  movzx   eax, word ptr [rbp+5Ah]
0x1400cef54  test    eax, eax
0x1400cef56  jnz     short loc_1400CEF6E
0x1400cef58  lea     rdx, [rbp+58h]
0x1400cef5c  jmp     short loc_1400CEF7A
0x1400cef5e  mov     rdx, rdi
0x1400cef61  mov     rcx, rbx
0x1400cef64  call    RtlpHpLfhContextMetadataFree
0x1400cef69  jmp     loc_1400CEE3B
0x1400cef6e  shl     eax, 6
0x1400cef71  mov     edx, eax
0x1400cef73  add     rdx, 10h
0x1400cef77  add     rdx, rbx
0x1400cef7a  lea     rax, [rdi+10h]
0x1400cef7e  sub     rax, rbx
0x1400cef81  lea     rcx, [rbp+50h]
0x1400cef85  sub     rax, 10h
0x1400cef89  shr     rax, 6
0x1400cef8d  mov     [rdx], ax
0x1400cef90  xor     eax, eax
0x1400cef92  mov     [rdi+10h], ax
0x1400cef96  movzx   eax, word ptr [rbp+5Ah]
0x1400cef9a  mov     [rdi+12h], ax
0x1400cef9e  movzx   edx, word ptr [rdx]
0x1400cefa1  mov     [rbp+5Ah], dx
0x1400cefa5  call    RtlpHpReleaseLockExclusive
0x1400cefaa  test    rsi, rsi
0x1400cefad  jz      short loc_1400CEFBD
0x1400cefaf  xor     r8d, r8d
0x1400cefb2  mov     rdx, rsi
0x1400cefb5  mov     rcx, rbx
0x1400cefb8  call    RtlpHpLfhContextMetadataFree
0x1400cefbd  mov     rax, rdi
0x1400cefc0  add     rsp, 28h
0x1400cefc4  pop     r15
0x1400cefc6  pop     r14
0x1400cefc8  pop     rdi
0x1400cefc9  pop     rsi
0x1400cefca  pop     rbp
0x1400cefcb  pop     rbx
0x1400cefcc  retn
```
