# FileProvBuildChunkTable

- ea: `0x140038ac0`
- end: `0x140038e3f`
- name: `FileProvBuildChunkTable`
- size: `895`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x140038260`

## callees

- `0x140007a30`
- `0x14000a140`
- `0x14000d3b8`
- `0x14000d440`
- `0x14000fb60`
- `0x1400119c0`
- `0x140038710`
- `0x140038ac0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140038ccd`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038cef`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038d81`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038d92`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038db7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038df6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038e07`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038ccd`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038cef`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038d81`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038d92`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038db7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038df6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038e07`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140038b8a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140038bc7`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140038b8a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140038bc7`

## string_xrefs

- `0x140038d70`: `Wof compressed file's resource table is corrupt`

## pseudocode

```c
__int64 __fastcall FileProvBuildChunkTable(__int64 a1, __int64 a2, volatile signed __int64 *a3)
{
  unsigned int *v5; // r12
  __int64 v6; // r8
  __int64 v7; // rdi
  unsigned int v8; // esi
  int v9; // r15d
  unsigned int v10; // ebx
  _QWORD *PoolWithTag; // r13
  unsigned int v12; // ebp
  __int64 v13; // rdx
  char *v14; // r14
  unsigned int v15; // esi
  __int64 v16; // r11
  unsigned __int64 v17; // r9
  __int64 v18; // rax
  unsigned __int64 v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // r10
  unsigned int v22; // edx
  __int16 v23; // r8
  _BYTE v25[224]; // [rsp+20h] [rbp-118h] BYREF
  char *P; // [rsp+158h] [rbp+20h]
  int Pa; // [rsp+158h] [rbp+20h]

  v5 = (unsigned int *)FileProvCompressionScheme(a2);
  memset(v25, 0, sizeof(v25));
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_3b099794e4b93327e327da255c047df6_Traceguids);
  v6 = *(_QWORD *)(a2 + 8);
  v7 = (*v5 + v6 - 1) / *v5;
  v8 = v7 - 1;
  if ( (_DWORD)v7 == 1 )
  {
    v15 = 0;
    goto LABEL_24;
  }
  if ( v8 > 0x1FFFFFFD )
  {
    v15 = -1073741670;
    goto LABEL_24;
  }
  v9 = 8;
  v10 = 1;
  if ( !HIDWORD(v6) )
    v9 = 4;
  PoolWithTag = ExAllocatePoolWithTag(PagedPool, 32LL * ((v8 + 14) / 0xD), 0x74637066u);
  if ( !PoolWithTag )
  {
    v15 = -1073741670;
    goto LABEL_24;
  }
  v12 = v8 * v9;
  P = (char *)ExAllocatePoolWithTag(PagedPool, (v8 * v9 + 4095) & 0xFFFFF000, 0x74637066u);
  if ( !P )
  {
    ExFreePoolWithTag(PoolWithTag, 0);
    v15 = -1073741670;
    goto LABEL_24;
  }
  FileProvInitializeCompletionContextOnStack(a1, v13, v25);
  v14 = P;
  Pa = FileProvReadCompressed(0, P, (v12 + 4095) & 0xFFFFF000, (__int64)v25);
  v15 = Pa;
  if ( Pa < 0 )
  {
    ExFreePoolWithTag(PoolWithTag, 0);
    ExFreePoolWithTag(v14, 0);
    goto LABEL_24;
  }
  v16 = 0;
  v17 = v12;
  *PoolWithTag = v12;
  while ( 1 )
  {
    if ( v10 == (_DWORD)v7 )
    {
      v18 = *(_QWORD *)(a2 + 16) - v12;
      goto LABEL_14;
    }
    if ( v10 > (unsigned int)v7 )
      break;
    if ( *(_DWORD *)(a2 + 12) )
      v18 = *(_QWORD *)&v14[v16];
    else
      v18 = *(unsigned int *)&v14[v16];
LABEL_14:
    v19 = v12 + v18;
    if ( v19 < v17 || (v20 = *v5, v19 + v20 < v17) || v19 > v20 + v17 )
    {
      MicrosoftTelemetryAssertTriggeredMsgKM("Wof compressed file's resource table is corrupt");
      ExFreePoolWithTag(PoolWithTag, 0);
      ExFreePoolWithTag(v14, 0);
      v15 = -1073700185;
      goto LABEL_24;
    }
    v21 = v10 / 0xD;
    v22 = v10 % 0xD;
    if ( v10 % 0xD )
    {
      v23 = v19 - v17;
      v16 = (unsigned int)(v9 + v16);
      v17 = v12 + v18;
      ++v10;
      *((_WORD *)&PoolWithTag[4 * v21] + v22 + 3) = v23;
    }
    else
    {
      v16 = (unsigned int)(v9 + v16);
      v17 = v12 + v18;
      ++v10;
      PoolWithTag[4 * v21] = v19;
    }
  }
  ExFreePoolWithTag(v14, 0);
  if ( _InterlockedCompareExchange64(a3, (signed __int64)PoolWithTag, 0) )
    ExFreePoolWithTag(PoolWithTag, 0);
  v15 = Pa;
LABEL_24:
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_3b099794e4b93327e327da255c047df6_Traceguids, v15);
  return v15;
}

```

## disassembly

```asm
0x140038ac0  mov     rax, rsp
0x140038ac3  mov     [rax+18h], r8
0x140038ac7  mov     [rax+10h], rdx
0x140038acb  push    rsi
0x140038acc  sub     rsp, 130h
0x140038ad3  mov     [rax+8], rbx
0x140038ad7  mov     rbx, rdx
0x140038ada  mov     [rax-18h], rdi
0x140038ade  mov     [rax-20h], r12
0x140038ae2  mov     [rax-30h], r14
0x140038ae6  mov     r14, rcx
0x140038ae9  mov     rcx, rdx
0x140038aec  call    FileProvCompressionScheme
0x140038af1  lea     rcx, [rsp+138h+var_118]; void *
0x140038af6  xor     edx, edx; Val
0x140038af8  mov     r8d, 0E0h; Size
0x140038afe  mov     r12, rax
0x140038b01  call    memset
0x140038b06  mov     rcx, cs:WPP_GLOBAL_Control
0x140038b0d  mov     eax, [rcx+2Ch]
0x140038b10  test    al, 20h
0x140038b12  jnz     loc_140038DCD
0x140038b18  mov     ecx, [r12]
0x140038b1c  mov     r8, [rbx+8]
0x140038b20  lea     rax, [r8-1]
0x140038b24  add     rax, rcx
0x140038b27  cqo
0x140038b29  idiv    rcx
0x140038b2c  mov     rdi, rax
0x140038b2f  lea     esi, [rax-1]
0x140038b32  test    esi, esi
0x140038b34  jz      loc_140038D61
0x140038b3a  cmp     esi, 1FFFFFFDh
0x140038b40  ja      loc_140038D69
0x140038b46  shr     r8, 20h
0x140038b4a  lea     ecx, [rsi+0Eh]
0x140038b4d  test    r8d, r8d
0x140038b50  mov     [rsp+138h+var_28], r13
0x140038b58  mov     eax, 4
0x140038b5d  mov     [rsp+138h+var_38], r15
0x140038b65  mov     r15d, 8
0x140038b6b  mov     ebx, 1
0x140038b70  cmovz   r15d, eax
0x140038b74  mov     r8d, 74637066h; Tag
0x140038b7a  mov     eax, 4EC4EC4Fh
0x140038b7f  mul     ecx
0x140038b81  mov     ecx, ebx; PoolType
0x140038b83  shr     edx, 2
0x140038b86  shl     rdx, 5; NumberOfBytes
0x140038b8a  call    cs:__imp_ExAllocatePoolWithTag
0x140038b91  nop     dword ptr [rax+rax+00h]
0x140038b96  mov     r13, rax
0x140038b99  test    rax, rax
0x140038b9c  jz      loc_140038DA8
0x140038ba2  mov     [rsp+138h+var_10], rbp
0x140038baa  mov     r8d, 74637066h; Tag
0x140038bb0  mov     ebp, r15d
0x140038bb3  mov     ecx, ebx; PoolType
0x140038bb5  imul    ebp, esi
0x140038bb8  lea     eax, [rbp+0FFFh]
0x140038bbe  and     eax, 0FFFFF000h
0x140038bc3  mov     edx, eax; NumberOfBytes
0x140038bc5  mov     esi, eax
0x140038bc7  call    cs:__imp_ExAllocatePoolWithTag
0x140038bce  nop     dword ptr [rax+rax+00h]
0x140038bd3  mov     [rsp+138h+P], rax
0x140038bdb  test    rax, rax
0x140038bde  jz      loc_140038DB2
0x140038be4  lea     r8, [rsp+138h+var_118]
0x140038be9  mov     rcx, r14
0x140038bec  call    FileProvInitializeCompletionContextOnStack
0x140038bf1  mov     r14, [rsp+138h+P]
0x140038bf9  lea     r9, [rsp+138h+var_118]
0x140038bfe  mov     rdx, r14
0x140038c01  mov     r8d, esi
0x140038c04  xor     ecx, ecx
0x140038c06  call    FileProvReadCompressed
0x140038c0b  mov     dword ptr [rsp+138h+P], eax
0x140038c12  mov     esi, eax
0x140038c14  test    eax, eax
0x140038c16  js      loc_140038DF1
0x140038c1c  mov     esi, ebp
0x140038c1e  xor     r11d, r11d
0x140038c21  mov     r9d, ebp
0x140038c24  mov     rbp, [rsp+138h+arg_8]
0x140038c2c  mov     [r13+0], rsi
0x140038c30  cmp     ebx, edi
0x140038c32  jz      short loc_140038CAA
0x140038c34  ja      loc_140038CC8
0x140038c3a  cmp     dword ptr [rbp+0Ch], 0
0x140038c3e  jnz     loc_140038D58
0x140038c44  mov     eax, [r11+r14]
0x140038c48  lea     rcx, [rsi+rax]
0x140038c4c  cmp     rcx, r9
0x140038c4f  jb      loc_140038D70
0x140038c55  mov     edx, [r12]
0x140038c59  lea     rax, [rcx+rdx]
0x140038c5d  cmp     rax, r9
0x140038c60  jb      loc_140038D70
0x140038c66  lea     rax, [rdx+r9]
0x140038c6a  cmp     rcx, rax
0x140038c6d  ja      loc_140038D70
0x140038c73  mov     eax, 4EC4EC4Fh
0x140038c78  mul     ebx
0x140038c7a  shr     edx, 2
0x140038c7d  imul    eax, edx, 0Dh
0x140038c80  mov     r10d, edx
0x140038c83  mov     edx, ebx
0x140038c85  sub     edx, eax
0x140038c87  jz      short loc_140038CB3
0x140038c89  dec     edx
0x140038c8b  shl     r10, 4
0x140038c8f  add     rdx, r10
0x140038c92  movzx   r8d, cx
0x140038c96  sub     r8w, r9w
0x140038c9a  add     r11d, r15d
0x140038c9d  mov     r9, rcx
0x140038ca0  inc     ebx
0x140038ca2  mov     [r13+rdx*2+8], r8w
0x140038ca8  jmp     short loc_140038C30
0x140038caa  mov     rax, [rbp+10h]
0x140038cae  sub     rax, rsi
0x140038cb1  jmp     short loc_140038C48
0x140038cb3  shl     r10, 5
0x140038cb7  add     r11d, r15d
0x140038cba  mov     r9, rcx
0x140038cbd  inc     ebx
0x140038cbf  mov     [r10+r13], rcx
0x140038cc3  jmp     loc_140038C30
0x140038cc8  xor     edx, edx; Tag
0x140038cca  mov     rcx, r14; P
0x140038ccd  call    cs:__imp_ExFreePoolWithTag
0x140038cd4  nop     dword ptr [rax+rax+00h]
0x140038cd9  mov     rcx, [rsp+138h+arg_10]
0x140038ce1  xor     eax, eax
0x140038ce3  lock cmpxchg [rcx], r13
0x140038ce8  jz      short loc_140038CFB
0x140038cea  xor     edx, edx; Tag
0x140038cec  mov     rcx, r13; P
0x140038cef  call    cs:__imp_ExFreePoolWithTag
0x140038cf6  nop     dword ptr [rax+rax+00h]
0x140038cfb  mov     esi, dword ptr [rsp+138h+P]
0x140038d02  mov     rbp, [rsp+138h+var_10]
0x140038d0a  mov     r13, [rsp+138h+var_28]
0x140038d12  mov     r15, [rsp+138h+var_38]
0x140038d1a  mov     rcx, cs:WPP_GLOBAL_Control
0x140038d21  mov     r14, [rsp+138h+var_30]
0x140038d29  mov     r12, [rsp+138h+var_20]
0x140038d31  mov     rdi, [rsp+138h+var_18]
0x140038d39  mov     eax, [rcx+2Ch]
0x140038d3c  mov     rbx, [rsp+138h+arg_0]
0x140038d44  test    al, 20h
0x140038d46  jnz     loc_140038E18
0x140038d4c  mov     eax, esi
0x140038d4e  add     rsp, 130h
0x140038d55  pop     rsi
0x140038d56  retn
0x140038d58  mov     rax, [r11+r14]
0x140038d5c  jmp     loc_140038C48
0x140038d61  xor     r11d, r11d
0x140038d64  mov     esi, r11d
0x140038d67  jmp     short loc_140038D1A
0x140038d69  mov     esi, 0C000009Ah
0x140038d6e  jmp     short loc_140038D1A
0x140038d70  lea     rcx, aWofCompressedF; "Wof compressed file's resource table is"...
0x140038d77  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140038d7c  xor     edx, edx; Tag
0x140038d7e  mov     rcx, r13; P
0x140038d81  call    cs:__imp_ExFreePoolWithTag
0x140038d88  nop     dword ptr [rax+rax+00h]
0x140038d8d  xor     edx, edx; Tag
0x140038d8f  mov     rcx, r14; P
0x140038d92  call    cs:__imp_ExFreePoolWithTag
0x140038d99  nop     dword ptr [rax+rax+00h]
0x140038d9e  mov     esi, 0C000A2A7h
0x140038da3  jmp     loc_140038D02
0x140038da8  mov     esi, 0C000009Ah
0x140038dad  jmp     loc_140038D0A
0x140038db2  xor     edx, edx; Tag
0x140038db4  mov     rcx, r13; P
0x140038db7  call    cs:__imp_ExFreePoolWithTag
0x140038dbe  nop     dword ptr [rax+rax+00h]
0x140038dc3  mov     esi, 0C000009Ah
0x140038dc8  jmp     loc_140038D02
0x140038dcd  cmp     byte ptr [rcx+29h], 4
0x140038dd1  jb      loc_140038B18
0x140038dd7  mov     rcx, [rcx+18h]
0x140038ddb  lea     r8, WPP_3b099794e4b93327e327da255c047df6_Traceguids
0x140038de2  mov     edx, 0Ah
0x140038de7  call    WPP_SF_
0x140038dec  jmp     loc_140038B18
0x140038df1  xor     edx, edx; Tag
0x140038df3  mov     rcx, r13; P
0x140038df6  call    cs:__imp_ExFreePoolWithTag
0x140038dfd  nop     dword ptr [rax+rax+00h]
0x140038e02  xor     edx, edx; Tag
0x140038e04  mov     rcx, r14; P
0x140038e07  call    cs:__imp_ExFreePoolWithTag
0x140038e0e  nop     dword ptr [rax+rax+00h]
0x140038e13  jmp     loc_140038D02
0x140038e18  cmp     byte ptr [rcx+29h], 4
0x140038e1c  jb      loc_140038D4C
0x140038e22  mov     rcx, [rcx+18h]
0x140038e26  lea     r8, WPP_3b099794e4b93327e327da255c047df6_Traceguids
0x140038e2d  mov     edx, 0Bh
0x140038e32  mov     r9d, esi
0x140038e35  call    WPP_SF_d
0x140038e3a  jmp     loc_140038D4C
```
