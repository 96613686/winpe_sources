# AddSingleBpColumnToKLLSketch(uchar *,unsigned __int64,uchar)

- ea: `0x10081a050`
- end: `0x10081a230`
- name: `?AddSingleBpColumnToKLLSketch@@YAXPEAE_KE@Z`
- size: `480`
- prototype: `void __fastcall(unsigned __int8 *, unsigned __int64, unsigned __int8)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x100819a80`
- `0x10081a050`

## import_xrefs

- `sqldk!SystemThread_TlsIndex` at `0x10081a06b`
- `sqldk!SystemThread_TlsOffset` at `0x10081a07c`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10081a097`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10081a097`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10081a199`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10081a199`

## pseudocode

```c
void __fastcall AddSingleBpColumnToKLLSketch(unsigned __int8 *a1, __int64 a2, unsigned __int8 a3)
{
  int v5; // edi
  _BYTE v6[8]; // [rsp+20h] [rbp-28h] BYREF
  __int64 v7; // [rsp+28h] [rbp-20h]
  char v8; // [rsp+60h] [rbp+18h] BYREF
  __int64 *v9; // [rsp+68h] [rbp+20h] BYREF

  v5 = a3;
  if ( !*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                  + SystemThread_TlsOffset
                  + 256LL) )
    SystemThread::MakeMiniSOSThread(0);
  switch ( v5 )
  {
    case '0':
    case 'h':
      LOBYTE(v7) = (unsigned __int64)a2 >> 1;
      break;
    case '4':
      LOWORD(v7) = a2 >> 1;
      break;
    case '8':
    case 'z':
      LODWORD(v7) = a2 >> 1;
      break;
    case ';':
      LODWORD(v7) = (unsigned __int64)a2 >> 1;
      break;
    case '<':
    case '\x7F':
      if ( (a2 & 1) != 0 )
        goto LABEL_8;
      v7 = a2 >> 1;
      break;
    case '>':
      if ( (a2 & 1) != 0 )
      {
LABEL_8:
        ((void (__fastcall *)(_QWORD, __int64, __int64 **, char *))*MEMORY[0])(0, a2, &v9, &v8);
        v7 = *v9;
      }
      else
      {
        v9 = (__int64 *)(a2 ^ (a2 ^ ((unsigned __int64)a2 >> 1)) & 0x1FFFFFFFFFFFFFFFLL);
        v7 = (__int64)v9;
      }
      break;
    default:
      ex_raise(98, 36, 16, 14);
      break;
  }
  AddSingleElementToKLLSketch(a1, (struct CXVariant *)v6, v5);
}

```

## disassembly

```asm
0x10081a050  mov     [rsp+arg_0], rbx
0x10081a055  mov     [rsp+arg_8], rsi
0x10081a05a  push    rdi
0x10081a05b  sub     rsp, 40h
0x10081a05f  mov     r11, gs:58h
0x10081a068  mov     rbx, rdx
0x10081a06b  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10081a072  mov     rsi, rcx
0x10081a075  movzx   edi, r8b
0x10081a079  mov     r10d, [rax]
0x10081a07c  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10081a083  mov     r9d, [rax]
0x10081a086  mov     rax, [r11+r10*8]
0x10081a08a  cmp     qword ptr [rax+r9+100h], 0
0x10081a093  jnz     short loc_10081A09D
0x10081a095  xor     ecx, ecx
0x10081a097  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10081a09d  lea     eax, [rdi-30h]; switch 80 cases
0x10081a0a0  cmp     eax, 4Fh
0x10081a0a3  ja      def_10081A0C4; jumptable 000000010081A0C4 default case, cases 49-51,53-55,57,58,61,63-103,105-121,123-126
0x10081a0a9  lea     rdx, ?tiBit@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiBit
0x10081a0b0  cdqe
0x10081a0b2  movzx   eax, ds:(byte_10081A1E0 - 100400000h)[rdx+rax]
0x10081a0ba  mov     ecx, ds:(jpt_10081A0C4 - 100400000h)[rdx+rax*4]
0x10081a0c1  add     rcx, rdx
0x10081a0c4  jmp     rcx; switch jump
0x10081a0c6  shr     rbx, 1; jumptable 000000010081A0C4 cases 48,104
0x10081a0c9  mov     byte ptr [rsp+48h+var_20], bl
0x10081a0cd  jmp     loc_10081A19F
0x10081a0d2  sar     rbx, 1; jumptable 000000010081A0C4 case 52
0x10081a0d5  mov     word ptr [rsp+48h+var_20], bx
0x10081a0da  jmp     loc_10081A19F
0x10081a0df  test    bl, 1; jumptable 000000010081A0C4 cases 60,127
0x10081a0e2  jnz     short loc_10081A0F1
0x10081a0e4  sar     rbx, 1
0x10081a0e7  mov     [rsp+48h+var_20], rbx
0x10081a0ec  jmp     loc_10081A19F
0x10081a0f1  mov     rax, ds:0
0x10081a0f9  lea     r9, [rsp+48h+arg_10]
0x10081a0fe  lea     r8, [rsp+48h+arg_18]
0x10081a103  mov     rdx, rbx
0x10081a106  xor     ecx, ecx
0x10081a108  call    qword ptr [rax]
0x10081a10a  mov     rax, [rsp+48h+arg_18]
0x10081a10f  mov     rbx, [rax]
0x10081a112  mov     [rsp+48h+var_20], rbx
0x10081a117  jmp     loc_10081A19F
0x10081a11c  shr     rbx, 1; jumptable 000000010081A0C4 case 59
0x10081a11f  mov     dword ptr [rsp+48h+var_20], ebx
0x10081a123  jmp     short loc_10081A19F
0x10081a125  test    bl, 1; jumptable 000000010081A0C4 case 62
0x10081a128  jnz     short loc_10081A156
0x10081a12a  mov     rax, rbx
0x10081a12d  mov     rcx, 1FFFFFFFFFFFFFFFh
0x10081a137  shr     rax, 1
0x10081a13a  xor     rax, rbx
0x10081a13d  and     rax, rcx
0x10081a140  xor     rax, rbx
0x10081a143  mov     [rsp+48h+arg_18], rax
0x10081a148  movsd   xmm0, [rsp+48h+arg_18]
0x10081a14e  movsd   [rsp+48h+var_20], xmm0
0x10081a154  jmp     short loc_10081A19F
0x10081a156  mov     rax, ds:0
0x10081a15e  lea     r9, [rsp+48h+arg_10]
0x10081a163  lea     r8, [rsp+48h+arg_18]
0x10081a168  mov     rdx, rbx
0x10081a16b  xor     ecx, ecx
0x10081a16d  call    qword ptr [rax]
0x10081a16f  mov     rax, [rsp+48h+arg_18]
0x10081a174  movsd   xmm0, qword ptr [rax]
0x10081a178  movsd   [rsp+48h+var_20], xmm0
0x10081a17e  jmp     short loc_10081A19F
0x10081a180  sar     rbx, 1; jumptable 000000010081A0C4 cases 56,122
0x10081a183  mov     dword ptr [rsp+48h+var_20], ebx
0x10081a187  jmp     short loc_10081A19F
0x10081a189  mov     edx, 24h ; '$'; jumptable 000000010081A0C4 default case, cases 49-51,53-55,57,58,61,63-103,105-121,123-126
0x10081a18e  lea     ecx, [rdx+3Eh]
0x10081a191  lea     r9d, [rdx-16h]
0x10081a195  lea     r8d, [rdx-14h]
0x10081a199  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x10081a19f  movzx   r8d, dil; unsigned __int8
0x10081a1a3  lea     rdx, [rsp+48h+var_28]; struct CXVariant *
0x10081a1a8  mov     rcx, rsi; unsigned __int8 *
0x10081a1ab  call    ?AddSingleElementToKLLSketch@@YAXPEAEPEAVCXVariant@@E@Z; AddSingleElementToKLLSketch(uchar *,CXVariant *,uchar)
0x10081a1b0  mov     rbx, [rsp+48h+arg_0]
0x10081a1b5  mov     rsi, [rsp+48h+arg_8]
0x10081a1ba  add     rsp, 40h
0x10081a1be  pop     rdi
0x10081a1bf  retn
```
