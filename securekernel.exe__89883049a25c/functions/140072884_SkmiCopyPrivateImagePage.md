# SkmiCopyPrivateImagePage

- ea: `0x140072884`
- end: `0x140072b13`
- name: `SkmiCopyPrivateImagePage`
- size: `655`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, int, __int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400111d0`

## callees

- `0x140002ef0`
- `0x140008118`
- `0x14000d020`
- `0x14000e130`
- `0x14000e460`
- `0x14000e810`
- `0x14000ff70`
- `0x140014c80`
- `0x14002d168`
- `0x14002f3f8`
- `0x140030f10`
- `0x14003a790`
- `0x14005fc00`
- `0x140072884`

## pseudocode

```c
__int64 __fastcall SkmiCopyPrivateImagePage(
        unsigned __int64 a1,
        unsigned __int64 a2,
        __int64 a3,
        ULONG_PTR a4,
        __int64 a5,
        unsigned __int64 a6)
{
  __int64 result; // rax
  __int64 v10; // rsi
  int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // r13
  int v14; // ebx
  int v15; // ecx
  char v16; // r9
  __int64 v17; // r8
  int v18; // ecx
  unsigned __int64 v19; // rdx
  __int64 *i; // rax
  __int64 v21; // r8
  __int64 v22; // r9
  char v23; // [rsp+30h] [rbp-49h]
  int v24[2]; // [rsp+38h] [rbp-41h] BYREF
  __int64 v25; // [rsp+40h] [rbp-39h]
  __int64 v26; // [rsp+48h] [rbp-31h]
  __int128 v27; // [rsp+50h] [rbp-29h] BYREF
  _OWORD v28[6]; // [rsp+60h] [rbp-19h] BYREF

  *(_QWORD *)v24 = 0;
  v27 = 0;
  memset(v28, 0, 32);
  result = SkobReferenceObjectByHandle(a2, 0, 1, (__int64)&SkmiImageType, v24, 0);
  if ( (int)result >= 0 )
  {
    v26 = SkiAttachProcess(a5);
    v25 = a5 + 8;
    v23 = SkAcquireSpinLockShared(a5 + 8);
    v10 = ((a6 >> 9) & 0x7FFFFFFFF8LL) - 0x98000000000LL;
    v11 = SkmiPrepareFaultChainForUpdate(a5, v10, (__int64)&v27, a1, 1);
    v13 = *(_QWORD *)v24;
    v14 = v11;
    if ( v11 < 0 )
    {
LABEL_24:
      LOBYTE(v12) = v23;
      RtlpReleasePropStoreLockShared(v25, v12);
      SkiAttachProcess(v26);
      SkobDereferenceObject(v13);
      return (unsigned int)v14;
    }
    if ( (v28[0] & 0x400) == 0 )
    {
      v15 = 257;
LABEL_5:
      SKMI_PAGE_SECURITY(v15, a1, v10, (__int64 *)v28);
      v14 = -1073741790;
LABEL_23:
      SkmiLockFaultChain(v10);
      SkmiCompleteFaultChain(v10, &v27);
      goto LABEL_24;
    }
    *(_QWORD *)v24 = *(_QWORD *)&v28[0];
    SKMI_UNSWIZZLE_INVALID_PTE(v24);
    v17 = qword_140156B00 + (*(__int64 *)v24 >> 16);
    if ( *(_QWORD *)(v17 + 56) == v13 )
    {
      v19 = (a6 >> 12) - (*(unsigned int *)(v17 + 24) | ((unsigned __int64)(*(_DWORD *)(v17 + 32) & 0xFFF) << 32));
      if ( v19 + *(unsigned int *)(v17 + 64) == a3 )
      {
        if ( v16 < 0
          || (*(_BYTE *)(v17 + 68) & (unsigned __int8)(*(_DWORD *)(*(_QWORD *)(v13 + 8) + 8 * a3) >> 10) & 1) != 0 )
        {
LABEL_21:
          v14 = SkmiCopyOnWrite(v13, a3, a1, a5, a4, (a6 >> 12 << 12) - (a3 << 12));
          if ( v14 >= 0 )
          {
            *(_QWORD *)v24 = (32
                            * (((a4 & 0xFFFFFFFFFFLL) << 7)
                             | (*(_QWORD *)&v28[0] >> 5) & 2LL
                             | (((*(_QWORD *)&v28[0] >> 5) & 4) != 0 ? 4LL : 1LL)))
                           | 0x802;
            SKMI_SWIZZLE_INVALID_PTE(v24, *(_QWORD *)v24, v21, v22);
            *(_QWORD *)&v28[0] = *(_QWORD *)v24;
          }
          goto LABEL_23;
        }
        for ( i = *(__int64 **)(a5 + 144); i != (__int64 *)(a5 + 144); i = (__int64 *)*i )
        {
          if ( !*((_DWORD *)i + 11) && i[2] == v17 )
          {
            if ( _bittest64(*(const signed __int64 **)(i[3] + 8), v19) )
              goto LABEL_21;
            break;
          }
        }
        v15 = 266;
        goto LABEL_5;
      }
      v18 = 261;
    }
    else
    {
      v18 = 267;
    }
    SKMI_SECURITY(v18);
    v14 = -1073741811;
    goto LABEL_23;
  }
  return result;
}

```

## disassembly

```asm
0x140072884  push    rbp
0x140072886  push    rbx
0x140072887  push    rsi
0x140072888  push    rdi
0x140072889  push    r12
0x14007288b  push    r13
0x14007288d  push    r14
0x14007288f  push    r15
0x140072891  lea     rbp, [rsp-0Fh]
0x140072896  sub     rsp, 88h
0x14007289d  xorps   xmm0, xmm0
0x1400728a0  mov     [rsp+0C0h+var_98], 0
0x1400728a9  mov     r15, rcx
0x1400728ac  mov     qword ptr [rbp+47h+var_88], 0
0x1400728b4  mov     rax, rdx
0x1400728b7  lea     rcx, [rbp+47h+var_88]
0x1400728bb  mov     [rsp+0C0h+BugCheckParameter3], rcx
0x1400728c0  mov     r14, r9
0x1400728c3  mov     r12, r8
0x1400728c6  lea     r9, SkmiImageType
0x1400728cd  mov     rcx, rax
0x1400728d0  mov     r8b, 1
0x1400728d3  xor     edx, edx
0x1400728d5  movups  [rbp+47h+var_70], xmm0
0x1400728d9  movups  [rbp+47h+var_60], xmm0
0x1400728dd  movups  [rbp+47h+var_50], xmm0
0x1400728e1  call    SkobReferenceObjectByHandle
0x1400728e6  test    eax, eax
0x1400728e8  js      loc_140072AFE
0x1400728ee  mov     rbx, [rbp+47h+arg_20]
0x1400728f2  mov     rcx, rbx
0x1400728f5  call    SkiAttachProcess
0x1400728fa  mov     [rbp+47h+var_78], rax
0x1400728fe  lea     rax, [rbx+8]
0x140072902  mov     rcx, rax
0x140072905  mov     [rbp+47h+var_80], rax
0x140072909  call    SkAcquireSpinLockShared
0x14007290e  mov     rdi, [rbp+47h+arg_28]
0x140072912  mov     rsi, rdi
0x140072915  mov     [rbp+47h+var_90], al
0x140072918  shr     rsi, 9
0x14007291c  mov     rax, 7FFFFFFFF8h
0x140072926  and     rsi, rax
0x140072929  mov     rax, 0FFFFF68000000000h
0x140072933  add     rsi, rax
0x140072936  mov     dword ptr [rsp+0C0h+BugCheckParameter3], 1
0x14007293e  mov     rdx, rsi
0x140072941  lea     r8, [rbp+47h+var_70]
0x140072945  mov     r9, r15
0x140072948  mov     rcx, rbx
0x14007294b  call    SkmiPrepareFaultChainForUpdate
0x140072950  mov     r13, qword ptr [rbp+47h+var_88]
0x140072954  mov     ebx, eax
0x140072956  test    eax, eax
0x140072958  js      loc_140072ADF
0x14007295e  mov     r9, qword ptr [rbp+47h+var_60]
0x140072962  bt      r9, 0Ah
0x140072967  jb      short loc_140072987
0x140072969  mov     ecx, 101h
0x14007296e  mov     rdx, r15
0x140072971  lea     r9, [rbp+47h+var_60]
0x140072975  mov     r8, rsi
0x140072978  call    SKMI_PAGE_SECURITY
0x14007297d  mov     ebx, 0C0000022h
0x140072982  jmp     loc_140072ACB
0x140072987  lea     rcx, [rbp+47h+var_88]
0x14007298b  mov     qword ptr [rbp+47h+var_88], r9
0x14007298f  call    SKMI_UNSWIZZLE_INVALID_PTE
0x140072994  mov     r8, qword ptr [rbp+47h+var_88]
0x140072998  sar     r8, 10h
0x14007299c  add     r8, cs:qword_140156B00
0x1400729a3  cmp     [r8+38h], r13
0x1400729a7  jz      short loc_1400729BD
0x1400729a9  mov     ecx, 10Bh
0x1400729ae  call    SKMI_SECURITY
0x1400729b3  mov     ebx, 0C000000Dh
0x1400729b8  jmp     loc_140072ACB
0x1400729bd  mov     ecx, [r8+20h]
0x1400729c1  mov     eax, [r8+18h]
0x1400729c5  and     ecx, 0FFFh
0x1400729cb  shl     rcx, 20h
0x1400729cf  or      rcx, rax
0x1400729d2  shr     rdi, 0Ch
0x1400729d6  mov     eax, [r8+40h]
0x1400729da  mov     rdx, rdi
0x1400729dd  sub     rdx, rcx
0x1400729e0  add     rax, rdx
0x1400729e3  cmp     rax, r12
0x1400729e6  jz      short loc_1400729EF
0x1400729e8  mov     ecx, 105h
0x1400729ed  jmp     short loc_1400729AE
0x1400729ef  test    r9b, r9b
0x1400729f2  mov     r9, [rbp+47h+arg_20]; int
0x1400729f6  js      short loc_140072A4C
0x1400729f8  mov     rax, [r13+8]
0x1400729fc  mov     ecx, [rax+r12*8]
0x140072a00  shr     rcx, 0Ah
0x140072a04  and     ecx, [r8+44h]
0x140072a08  test    cl, 1
0x140072a0b  jnz     short loc_140072A4C
0x140072a0d  lea     rcx, [r9+90h]
0x140072a14  mov     rax, [rcx]
0x140072a17  jmp     short loc_140072A28
0x140072a19  cmp     dword ptr [rax+2Ch], 0
0x140072a1d  jnz     short loc_140072A25
0x140072a1f  cmp     [rax+10h], r8
0x140072a23  jz      short loc_140072A2F
0x140072a25  mov     rax, [rax]
0x140072a28  cmp     rax, rcx
0x140072a2b  jnz     short loc_140072A19
0x140072a2d  jmp     short loc_140072A42
0x140072a2f  mov     rax, [rax+18h]
0x140072a33  mov     rcx, [rax+8]
0x140072a37  bt      [rcx], rdx
0x140072a3b  setb    al
0x140072a3e  test    al, al
0x140072a40  jnz     short loc_140072A4C
0x140072a42  mov     ecx, 10Ah
0x140072a47  jmp     loc_14007296E
0x140072a4c  mov     rax, r12
0x140072a4f  shl     rdi, 0Ch
0x140072a53  shl     rax, 0Ch
0x140072a57  mov     r8, r15; int
0x140072a5a  sub     rdi, rax
0x140072a5d  mov     rdx, r12; int
0x140072a60  mov     [rsp+0C0h+var_98], rdi; __int64
0x140072a65  mov     rcx, r13; int
0x140072a68  mov     [rsp+0C0h+BugCheckParameter3], r14; BugCheckParameter3
0x140072a6d  call    SkmiCopyOnWrite
0x140072a72  mov     ebx, eax
0x140072a74  test    eax, eax
0x140072a76  js      short loc_140072ACB
0x140072a78  mov     rcx, qword ptr [rbp+47h+var_60]
0x140072a7c  shr     rcx, 5
0x140072a80  mov     al, cl
0x140072a82  and     al, 4
0x140072a84  neg     al
0x140072a86  mov     eax, ecx
0x140072a88  lea     rcx, [rbp+47h+var_88]
0x140072a8c  sbb     rdx, rdx
0x140072a8f  and     eax, 2
0x140072a92  and     edx, 3
0x140072a95  inc     rdx
0x140072a98  or      rdx, rax
0x140072a9b  mov     rax, 0FFFFFFFFFFh
0x140072aa5  and     r14, rax
0x140072aa8  shl     r14, 7
0x140072aac  or      rdx, r14
0x140072aaf  shl     rdx, 5
0x140072ab3  or      rdx, 802h
0x140072aba  mov     qword ptr [rbp+47h+var_88], rdx
0x140072abe  call    SKMI_SWIZZLE_INVALID_PTE
0x140072ac3  mov     r9, qword ptr [rbp+47h+var_88]
0x140072ac7  mov     qword ptr [rbp+47h+var_60], r9
0x140072acb  mov     rcx, rsi
0x140072ace  call    SkmiLockFaultChain
0x140072ad3  lea     rdx, [rbp+47h+var_70]
0x140072ad7  mov     rcx, rsi
0x140072ada  call    SkmiCompleteFaultChain
0x140072adf  mov     dl, [rbp+47h+var_90]
0x140072ae2  mov     rcx, [rbp+47h+var_80]
0x140072ae6  call    RtlpReleasePropStoreLockShared
0x140072aeb  mov     rcx, [rbp+47h+var_78]
0x140072aef  call    SkiAttachProcess
0x140072af4  mov     rcx, r13
0x140072af7  call    SkobDereferenceObject
0x140072afc  mov     eax, ebx
0x140072afe  add     rsp, 88h
0x140072b05  pop     r15
0x140072b07  pop     r14
0x140072b09  pop     r13
0x140072b0b  pop     r12
0x140072b0d  pop     rdi
0x140072b0e  pop     rsi
0x140072b0f  pop     rbx
0x140072b10  pop     rbp
0x140072b11  retn
```
