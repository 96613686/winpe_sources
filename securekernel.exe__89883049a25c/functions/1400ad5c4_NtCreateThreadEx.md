# NtCreateThreadEx

- ea: `0x1400ad5c4`
- end: `0x1400adaf0`
- name: `NtCreateThreadEx`
- size: `1324`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: ``

## callees

- `0x140002ef0`
- `0x1400119c4`
- `0x140033a00`
- `0x140037e84`
- `0x140040c7c`
- `0x1400442ac`
- `0x1400442ec`
- `0x1400a1128`
- `0x1400ad5c4`
- `0x1400d4e8c`
- `0x1400f02d0`
- `0x1400f38f0`
- `0x1400fc664`
- `0x1400fc7c0`

## pseudocode

```c
__int64 __fastcall NtCreateThreadEx(
        __int64 *a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        unsigned __int64 a5,
        unsigned __int64 a6,
        int a7,
        __int64 a8,
        unsigned __int64 a9,
        unsigned __int64 a10,
        char *a11)
{
  _QWORD *v12; // r15
  __int64 *v13; // r12
  __int64 v15; // rcx
  char v16; // r14
  __int64 ULong64FromUser; // rax
  unsigned __int64 v18; // rsi
  unsigned __int64 v19; // rsi
  unsigned __int64 v20; // rsi
  char *v21; // rbx
  _QWORD *v22; // rax
  __int64 v23; // rdx
  int v24; // esi
  _QWORD *v25; // r13
  __int64 v26; // rbx
  int v27; // eax
  __int64 v28; // rbx
  __int64 v29; // rdx
  __int64 v30; // rdx
  __int64 v31; // [rsp+68h] [rbp-D0h] BYREF
  unsigned __int64 v32; // [rsp+70h] [rbp-C8h]
  __int64 v33; // [rsp+78h] [rbp-C0h]
  __int64 v34; // [rsp+80h] [rbp-B8h]
  __int64 v35; // [rsp+88h] [rbp-B0h] BYREF
  __int64 v36; // [rsp+90h] [rbp-A8h]
  __int128 v37; // [rsp+98h] [rbp-A0h] BYREF
  __int128 Address; // [rsp+A8h] [rbp-90h]
  __int128 v39; // [rsp+B8h] [rbp-80h] BYREF
  unsigned __int128 v40; // [rsp+C8h] [rbp-70h]
  unsigned __int128 v41; // [rsp+D8h] [rbp-60h]
  __int64 v42; // [rsp+E8h] [rbp-50h]
  char *v43; // [rsp+F0h] [rbp-48h]
  _QWORD *StackBase; // [rsp+F8h] [rbp-40h]

  v37 = 0;
  Address = 0;
  v35 = 0;
  v39 = 0;
  v40 = 0;
  v41 = 0;
  LODWORD(v42) = 0;
  v12 = 0;
  v34 = 0;
  v13 = 0;
  v33 = 0;
  if ( a4 != -1 )
    return 3221225659LL;
  StackBase = KeGetPcr()->NtTib.StackBase;
  v15 = StackBase[10];
  v36 = v15;
  v16 = *((_BYTE *)StackBase + 96);
  if ( v16 == 1 )
  {
    ULong64FromUser = RtlReadULong64FromUser(a1);
    RtlWriteULong64ToUser(a1, ULong64FromUser);
  }
  if ( a11 )
  {
    if ( v16 )
    {
      if ( ((unsigned __int8)a11 & 3) != 0 )
        ExRaiseDatatypeMisalignment();
      v18 = RtlReadULong64FromUser(a11);
    }
    else
    {
      v18 = *(_QWORD *)a11;
    }
    v32 = v18;
    if ( v18 < 0x28 )
      return 3221225485LL;
    if ( v16 )
      ProbeForRead(a11 + 40, v18 - 40, 4u);
    v19 = v18 - 8;
    v32 = v19;
    if ( (v19 & 0x1F) != 0 )
      return 3221225485LL;
    v20 = v19 >> 5;
    v32 = v20;
    v21 = a11 + 8;
    v43 = a11 + 8;
    while ( v20 )
    {
      if ( v16 )
        RtlCopyFromUser(&v37, v21, 0x20u);
      else
        RtlCopyVolatileMemory(&v37, v21, 0x20u);
      if ( (v37 & 0x20000) != 0 && *((_QWORD *)&Address + 1) )
        return 3221225485LL;
      if ( (_QWORD)v37 == 65539 )
      {
        v15 = 16;
        if ( *((_QWORD *)&v37 + 1) != 16 )
          return 3221225485LL;
        v12 = (_QWORD *)Address;
        v34 = Address;
        if ( v16 )
        {
          ProbeForWrite((volatile void *)Address, 0x10u, 4u);
          v15 = 16;
        }
        v22 = (_QWORD *)*((_QWORD *)&Address + 1);
        if ( *((_QWORD *)&Address + 1) )
        {
          if ( v16 )
          {
            if ( (BYTE8(Address) & 3) != 0 )
              ExRaiseDatatypeMisalignment();
            v23 = 16;
LABEL_44:
            RtlWriteULong64ToUser(v22, v23);
            goto LABEL_46;
          }
          **((_QWORD **)&Address + 1) = 16;
        }
      }
      else
      {
        if ( (_QWORD)v37 != 65540 )
          return 3221225485LL;
        if ( *((_QWORD *)&v37 + 1) != 8 )
          return 3221225485LL;
        v13 = (__int64 *)Address;
        v33 = Address;
        if ( v16 )
          ProbeForWrite((volatile void *)Address, 8u, 4u);
        v22 = (_QWORD *)*((_QWORD *)&Address + 1);
        if ( *((_QWORD *)&Address + 1) )
        {
          if ( !v16 )
          {
            **((_QWORD **)&Address + 1) = 8;
            goto LABEL_46;
          }
          if ( (BYTE8(Address) & 3) != 0 )
            ExRaiseDatatypeMisalignment();
          v23 = 8;
          goto LABEL_44;
        }
      }
LABEL_46:
      v21 += 32;
      v43 = v21;
      v32 = --v20;
    }
  }
  v31 = 0;
  LOBYTE(v15) = v16 == 0;
  v24 = SkobReserveHandle(v15, &v31);
  if ( v24 < 0 )
    goto LABEL_66;
  LODWORD(v39) = 8;
  v40 = __PAIR128__(a6, a5);
  *((_QWORD *)&v39 + 1) = v36;
  v41 = __PAIR128__(a10, a9);
  v42 = 0;
  v25 = StackBase;
  v26 = StackBase[33];
  StackBase[33] = &v39;
  v27 = NkCreateThreadEx(&v35, a2, a3, -1, *((unsigned int *)v25 + 42), 0, a7, a8, a9, a10, 0);
  v24 = v27;
  v25[33] = v26;
  if ( !v42 )
  {
    if ( v27 >= 0 )
      v24 = -1073741823;
LABEL_66:
    if ( v31 )
      SkobDeleteReservedHandle();
    return (unsigned int)v24;
  }
  if ( v27 < 0 )
    SkeBugCheckEx(0x29u, 0x68547243u, v27, 0, 0);
  v28 = v31;
  SkobMakeReservedHandleValid(v31, v42, v35);
  if ( v12 )
  {
    if ( v16 )
      RtlWriteULong64ToUser(v12, *(_QWORD *)(v36 + 56));
    else
      *v12 = *(_QWORD *)(v36 + 56);
    v29 = *(_QWORD *)(v42 + 208);
    if ( v16 )
      RtlWriteULong64ToUser(v12 + 1, v29);
    else
      v12[1] = v29;
  }
  if ( v13 )
  {
    v30 = *(_QWORD *)(v42 + 160);
    if ( v16 )
      RtlWriteULong64ToUser(v13, v30);
    else
      *v13 = v30;
  }
  SkobDereferenceObject(v42);
  if ( v16 )
    RtlWriteULong64ToUser(a1, v28);
  else
    *a1 = v28;
  return (unsigned int)v24;
}

```

## disassembly

```asm
0x1400ad5c4  mov     rax, rsp
0x1400ad5c7  mov     [rax+20h], r9
0x1400ad5cb  mov     [rax+18h], r8
0x1400ad5cf  mov     [rax+10h], edx
0x1400ad5d2  mov     [rax+8], rcx
0x1400ad5d6  push    rbx
0x1400ad5d7  push    rsi
0x1400ad5d8  push    r12
0x1400ad5da  push    r13
0x1400ad5dc  push    r14
0x1400ad5de  push    r15
0x1400ad5e0  sub     rsp, 108h
0x1400ad5e7  mov     rbx, rcx
0x1400ad5ea  mov     qword ptr [rax-0B8h], 0
0x1400ad5f5  xorps   xmm0, xmm0
0x1400ad5f8  movups  xmmword ptr [rax-0A0h], xmm0
0x1400ad5ff  movups  xmmword ptr [rax-90h], xmm0
0x1400ad606  mov     qword ptr [rax-0B0h], 0
0x1400ad611  mov     [rsp+138h+var_C0], 0
0x1400ad61a  xor     ecx, ecx
0x1400ad61c  movups  xmmword ptr [rax-80h], xmm0
0x1400ad620  movups  xmmword ptr [rax-70h], xmm0
0x1400ad624  movups  xmmword ptr [rax-60h], xmm0
0x1400ad628  mov     [rax-50h], ecx
0x1400ad62b  xor     r15d, r15d
0x1400ad62e  mov     [rax-0B8h], r15
0x1400ad635  xor     r12d, r12d
0x1400ad638  mov     [rsp+138h+var_C0], r12
0x1400ad63d  cmp     r9, 0FFFFFFFFFFFFFFFFh
0x1400ad641  jz      short loc_1400AD64D
0x1400ad643  mov     eax, 0C00000BBh
0x1400ad648  jmp     loc_1400ADAAE
0x1400ad64d  mov     rax, gs:8
0x1400ad656  mov     [rsp+138h+var_40], rax
0x1400ad65e  mov     rcx, [rax+50h]
0x1400ad662  mov     [rsp+138h+var_A8], rcx
0x1400ad66a  mov     r14b, [rax+60h]
0x1400ad66e  mov     [rsp+138h+var_D8], r14b
0x1400ad673  cmp     r14b, 1
0x1400ad677  jnz     short loc_1400AD693
0x1400ad679  mov     rcx, rbx
0x1400ad67c  call    RtlReadULong64FromUser
0x1400ad681  mov     rdx, rax
0x1400ad684  mov     rcx, rbx
0x1400ad687  call    RtlWriteULong64ToUser
0x1400ad68c  jmp     short loc_1400AD693
0x1400ad68e  jmp     loc_1400ADAAE
0x1400ad693  mov     rbx, [rsp+138h+arg_50]
0x1400ad69b  test    rbx, rbx
0x1400ad69e  jz      loc_1400AD886
0x1400ad6a4  test    r14b, r14b
0x1400ad6a7  jz      short loc_1400AD6C4
0x1400ad6a9  test    bl, 3
0x1400ad6ac  jnz     loc_1400ADAC1
0x1400ad6b2  test    r14b, r14b
0x1400ad6b5  jz      short loc_1400AD6C4
0x1400ad6b7  mov     rcx, rbx
0x1400ad6ba  call    RtlReadULong64FromUser
0x1400ad6bf  mov     rsi, rax
0x1400ad6c2  jmp     short loc_1400AD6C7
0x1400ad6c4  mov     rsi, [rbx]
0x1400ad6c7  mov     [rsp+138h+var_C8], rsi
0x1400ad6cc  cmp     rsi, 28h ; '('
0x1400ad6d0  jnb     short loc_1400AD6DC
0x1400ad6d2  mov     eax, 0C000000Dh
0x1400ad6d7  jmp     loc_1400ADAAE
0x1400ad6dc  test    r14b, r14b
0x1400ad6df  jz      short loc_1400AD6F4
0x1400ad6e1  lea     rdx, [rsi-28h]; Length
0x1400ad6e5  lea     rcx, [rbx+28h]; Address
0x1400ad6e9  mov     r8d, 4; Alignment
0x1400ad6ef  call    ProbeForRead
0x1400ad6f4  add     rsi, 0FFFFFFFFFFFFFFF8h
0x1400ad6f8  mov     [rsp+138h+var_C8], rsi
0x1400ad6fd  test    sil, 1Fh
0x1400ad701  jz      short loc_1400AD70D
0x1400ad703  mov     eax, 0C000000Dh
0x1400ad708  jmp     loc_1400ADAAE
0x1400ad70d  shr     rsi, 5
0x1400ad711  mov     [rsp+138h+var_C8], rsi
0x1400ad716  add     rbx, 8
0x1400ad71a  mov     [rsp+138h+var_48], rbx
0x1400ad722  mov     r13d, 8
0x1400ad728  test    rsi, rsi
0x1400ad72b  jz      loc_1400AD87F
0x1400ad731  mov     r8d, 20h ; ' '; Size
0x1400ad737  mov     rdx, rbx; Src
0x1400ad73a  lea     rcx, [rsp+138h+var_A0]; void *
0x1400ad742  test    r14b, r14b
0x1400ad745  jz      short loc_1400AD74E
0x1400ad747  call    RtlCopyFromUser
0x1400ad74c  jmp     short loc_1400AD753
0x1400ad74e  call    RtlCopyVolatileMemory
0x1400ad753  mov     rax, [rsp+138h+var_A0]
0x1400ad75b  bt      rax, 11h
0x1400ad760  jnb     short loc_1400AD777
0x1400ad762  cmp     [rsp+138h+var_88], 0
0x1400ad76b  jz      short loc_1400AD777
0x1400ad76d  mov     eax, 0C000000Dh
0x1400ad772  jmp     loc_1400ADAAE
0x1400ad777  sub     rax, 10003h
0x1400ad77d  jz      short loc_1400AD7F3
0x1400ad77f  cmp     rax, 1
0x1400ad783  jz      short loc_1400AD78F
0x1400ad785  mov     eax, 0C000000Dh
0x1400ad78a  jmp     loc_1400ADAAE
0x1400ad78f  cmp     [rsp+138h+var_98], r13
0x1400ad797  jz      short loc_1400AD7A3
0x1400ad799  mov     eax, 0C000000Dh
0x1400ad79e  jmp     loc_1400ADAAE
0x1400ad7a3  mov     r12, [rsp+138h+Address]
0x1400ad7ab  mov     [rsp+138h+var_C0], r12
0x1400ad7b0  test    r14b, r14b
0x1400ad7b3  jz      short loc_1400AD7C6
0x1400ad7b5  mov     r8d, 4; Alignment
0x1400ad7bb  mov     rdx, r13; Length
0x1400ad7be  mov     rcx, r12; Address
0x1400ad7c1  call    ProbeForWrite
0x1400ad7c6  mov     rax, [rsp+138h+var_88]
0x1400ad7ce  test    rax, rax
0x1400ad7d1  jz      loc_1400AD866
0x1400ad7d7  test    r14b, r14b
0x1400ad7da  jz      short loc_1400AD7EE
0x1400ad7dc  test    al, 3
0x1400ad7de  jnz     loc_1400ADAC7
0x1400ad7e4  test    r14b, r14b
0x1400ad7e7  jz      short loc_1400AD7EE
0x1400ad7e9  mov     rdx, r13
0x1400ad7ec  jmp     short loc_1400AD859
0x1400ad7ee  mov     [rax], r13
0x1400ad7f1  jmp     short loc_1400AD866
0x1400ad7f3  mov     ecx, 10h
0x1400ad7f8  cmp     [rsp+138h+var_98], rcx
0x1400ad800  jz      short loc_1400AD80C
0x1400ad802  mov     eax, 0C000000Dh
0x1400ad807  jmp     loc_1400ADAAE
0x1400ad80c  mov     r15, [rsp+138h+Address]
0x1400ad814  mov     [rsp+138h+var_B8], r15
0x1400ad81c  test    r14b, r14b
0x1400ad81f  jz      short loc_1400AD837
0x1400ad821  mov     r8d, 4; Alignment
0x1400ad827  mov     rdx, rcx; Length
0x1400ad82a  mov     rcx, r15; Address
0x1400ad82d  call    ProbeForWrite
0x1400ad832  mov     ecx, 10h
0x1400ad837  mov     rax, [rsp+138h+var_88]
0x1400ad83f  test    rax, rax
0x1400ad842  jz      short loc_1400AD866
0x1400ad844  test    r14b, r14b
0x1400ad847  jz      short loc_1400AD863
0x1400ad849  test    al, 3
0x1400ad84b  jnz     loc_1400ADACC
0x1400ad851  test    r14b, r14b
0x1400ad854  jz      short loc_1400AD863
0x1400ad856  mov     rdx, rcx
0x1400ad859  mov     rcx, rax
0x1400ad85c  call    RtlWriteULong64ToUser
0x1400ad861  jmp     short loc_1400AD866
0x1400ad863  mov     [rax], rcx
0x1400ad866  add     rbx, 20h ; ' '
0x1400ad86a  mov     [rsp+138h+var_48], rbx
0x1400ad872  dec     rsi
0x1400ad875  mov     [rsp+138h+var_C8], rsi
0x1400ad87a  jmp     loc_1400AD728
0x1400ad87f  jmp     short loc_1400AD88C
0x1400ad881  jmp     loc_1400ADAAE
0x1400ad886  mov     r13d, 8
0x1400ad88c  mov     [rsp+138h+var_D0], 0
0x1400ad895  test    r14b, r14b
0x1400ad898  setz    cl
0x1400ad89b  lea     rdx, [rsp+138h+var_D0]
0x1400ad8a0  call    SkobReserveHandle
0x1400ad8a5  mov     esi, eax
0x1400ad8a7  test    eax, eax
0x1400ad8a9  js      loc_1400ADA9D
0x1400ad8af  mov     [rsp+138h+var_80], r13d
0x1400ad8b7  mov     rax, [rsp+138h+arg_20]
0x1400ad8bf  mov     [rsp+138h+var_70], rax
0x1400ad8c7  mov     rax, [rsp+138h+arg_28]
0x1400ad8cf  mov     [rsp+138h+var_68], rax
0x1400ad8d7  mov     rax, [rsp+138h+var_A8]
0x1400ad8df  mov     [rsp+138h+var_78], rax
0x1400ad8e7  mov     rdx, [rsp+138h+arg_40]
0x1400ad8ef  mov     [rsp+138h+var_60], rdx
0x1400ad8f7  mov     rax, [rsp+138h+arg_48]
0x1400ad8ff  mov     [rsp+138h+var_58], rax
0x1400ad907  mov     [rsp+138h+var_50], 0
0x1400ad913  mov     r13, [rsp+138h+var_40]
0x1400ad91b  mov     rbx, [r13+108h]
0x1400ad922  lea     rcx, [rsp+138h+var_80]
0x1400ad92a  mov     [r13+108h], rcx
0x1400ad931  mov     ecx, [r13+0A8h]
0x1400ad938  mov     [rsp+138h+var_E8], 0
0x1400ad941  mov     [rsp+138h+var_F0], rax
0x1400ad946  mov     [rsp+138h+var_F8], rdx
0x1400ad94b  mov     rax, [rsp+138h+arg_38]
0x1400ad953  mov     [rsp+138h+var_100], rax
0x1400ad958  mov     eax, [rsp+138h+arg_30]
0x1400ad95f  mov     [rsp+138h+var_108], eax
0x1400ad963  mov     [rsp+138h+var_110], 0
0x1400ad96c  mov     [rsp+138h+BugCheckParameter4], rcx
0x1400ad971  mov     r9, [rsp+138h+arg_18]
0x1400ad979  mov     r8, [rsp+138h+arg_10]
0x1400ad981  mov     edx, [rsp+138h+arg_8]
0x1400ad988  lea     rcx, [rsp+138h+var_B0]
0x1400ad990  call    NkCreateThreadEx
0x1400ad995  movsxd  rsi, eax
0x1400ad998  mov     dword ptr [rsp+138h+arg_18], esi
0x1400ad99f  mov     [r13+108h], rbx
0x1400ad9a6  mov     rdx, [rsp+138h+var_50]
0x1400ad9ae  test    rdx, rdx
0x1400ad9b1  jz      loc_1400ADA93
0x1400ad9b7  test    eax, eax
0x1400ad9b9  js      loc_1400ADAD2
0x1400ad9bf  mov     r8, [rsp+138h+var_B0]
0x1400ad9c7  mov     rbx, [rsp+138h+var_D0]
0x1400ad9cc  mov     rcx, rbx
0x1400ad9cf  call    SkobMakeReservedHandleValid
0x1400ad9d4  nop
0x1400ad9d5  test    r15, r15
0x1400ad9d8  jz      short loc_1400ADA1E
0x1400ad9da  mov     rax, [rsp+138h+var_A8]
0x1400ad9e2  mov     rax, [rax+38h]
0x1400ad9e6  test    r14b, r14b
0x1400ad9e9  jz      short loc_1400AD9F8
0x1400ad9eb  mov     rdx, rax
0x1400ad9ee  mov     rcx, r15
0x1400ad9f1  call    RtlWriteULong64ToUser
0x1400ad9f6  jmp     short loc_1400AD9FB
0x1400ad9f8  mov     [r15], rax
0x1400ad9fb  mov     rax, [rsp+138h+var_50]
0x1400ada03  mov     rdx, [rax+0D0h]
0x1400ada0a  test    r14b, r14b
0x1400ada0d  jz      short loc_1400ADA1A
0x1400ada0f  lea     rcx, [r15+8]
0x1400ada13  call    RtlWriteULong64ToUser
0x1400ada18  jmp     short loc_1400ADA1E
0x1400ada1a  mov     [r15+8], rdx
0x1400ada1e  test    r12, r12
0x1400ada21  jz      short loc_1400ADA45
0x1400ada23  mov     rax, [rsp+138h+var_50]
0x1400ada2b  mov     rdx, [rax+0A0h]
0x1400ada32  test    r14b, r14b
0x1400ada35  jz      short loc_1400ADA41
0x1400ada37  mov     rcx, r12
0x1400ada3a  call    RtlWriteULong64ToUser
0x1400ada3f  jmp     short loc_1400ADA45
0x1400ada41  mov     [r12], rdx
0x1400ada45  jmp     short loc_1400ADA58
0x1400ada47  mov     r14b, [rsp+138h+var_D8]
0x1400ada4c  mov     rbx, [rsp+138h+var_D0]
0x1400ada51  mov     esi, dword ptr [rsp+138h+arg_18]
0x1400ada58  mov     rcx, [rsp+138h+var_50]
0x1400ada60  call    SkobDereferenceObject
0x1400ada65  nop
0x1400ada66  test    r14b, r14b
0x1400ada69  jz      short loc_1400ADA7D
0x1400ada6b  mov     rdx, rbx
0x1400ada6e  mov     rcx, [rsp+138h+arg_0]
0x1400ada76  call    RtlWriteULong64ToUser
0x1400ada7b  jmp     short loc_1400ADA88
0x1400ada7d  mov     rax, [rsp+138h+arg_0]
0x1400ada85  mov     [rax], rbx
0x1400ada88  jmp     short loc_1400ADAAC
0x1400ada8a  mov     esi, dword ptr [rsp+138h+arg_18]
0x1400ada91  jmp     short loc_1400ADAAC
0x1400ada93  mov     eax, 0C0000001h
0x1400ada98  test    esi, esi
0x1400ada9a  cmovns  esi, eax
0x1400ada9d  mov     rcx, [rsp+138h+var_D0]
0x1400adaa2  test    rcx, rcx
0x1400adaa5  jz      short loc_1400ADAAC
0x1400adaa7  call    SkobDeleteReservedHandle
0x1400adaac  mov     eax, esi
0x1400adaae  add     rsp, 108h
0x1400adab5  pop     r15
0x1400adab7  pop     r14
0x1400adab9  pop     r13
0x1400adabb  pop     r12
0x1400adabd  pop     rsi
0x1400adabe  pop     rbx
0x1400adabf  retn
0x1400adac1  call    ExRaiseDatatypeMisalignment
0x1400adac7  call    ExRaiseDatatypeMisalignment
0x1400adacc  call    ExRaiseDatatypeMisalignment
0x1400adad2  mov     r8, rsi; BugCheckParameter2
0x1400adad5  mov     [rsp+138h+BugCheckParameter4], 0; BugCheckParameter4
0x1400adade  xor     r9d, r9d; BugCheckParameter3
0x1400adae1  mov     edx, 68547243h; BugCheckParameter1
0x1400adae6  lea     ecx, [r9+29h]; BugCheckCode
0x1400adaea  call    SkeBugCheckEx
```
