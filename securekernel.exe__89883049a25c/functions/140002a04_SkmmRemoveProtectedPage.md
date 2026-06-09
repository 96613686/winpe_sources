# SkmmRemoveProtectedPage

- ea: `0x140002a04`
- end: `0x140002e36`
- name: `SkmmRemoveProtectedPage`
- size: `1074`
- prototype: `__int64 __fastcall(ULONG_PTR BugCheckParameter3)`
- caller_count: `1`
- callee_count: `22`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x140014dd0`

## callees

- `0x140002a04`
- `0x140002e40`
- `0x140002ef0`
- `0x140002f60`
- `0x140008118`
- `0x1400091e0`
- `0x14000d060`
- `0x14000e460`
- `0x14000e810`
- `0x14000ff70`
- `0x140014c80`
- `0x1400202b0`
- `0x1400273c8`
- `0x14002b1e0`
- `0x14002d168`
- `0x14002f3f8`
- `0x140033abc`
- `0x14003a790`
- `0x14005449c`
- `0x1400731c0`
- `0x1400a1950`
- `0x1400f2fc0`

## pseudocode

```c
__int64 __fastcall SkmmRemoveProtectedPage(ULONG_PTR BugCheckParameter3, unsigned __int64 *a2, int a3)
{
  unsigned __int64 v4; // r10
  unsigned int v6; // ebx
  __int64 v7; // rdi
  unsigned __int64 v8; // r14
  unsigned __int64 v9; // r10
  char v10; // si
  volatile signed __int64 *HandleEntry; // rax
  volatile signed __int64 *v12; // r8
  signed __int64 v13; // rbx
  signed __int64 v14; // rdx
  signed __int64 v15; // rax
  unsigned __int64 v16; // rbx
  unsigned __int16 v17; // ax
  unsigned __int16 v18; // dx
  __int64 v19; // rcx
  _DWORD *v20; // rsi
  unsigned __int64 v21; // r14
  __int64 (__fastcall **v22)(ULONG_PTR); // rax
  __int64 *v23; // rdi
  char v24; // al
  __int64 *v25; // r8
  char v26; // bl
  int v27; // r9d
  __int64 v28; // rcx
  __int64 v29; // r12
  char v30; // r13
  __int64 v31; // r14
  int v32; // eax
  __int64 v33; // rdx
  __int64 v34; // rdx
  __int64 v35; // r8
  __int64 v36; // r9
  __int128 v38; // [rsp+30h] [rbp-78h] BYREF
  _OWORD v39[6]; // [rsp+40h] [rbp-68h] BYREF
  __int64 v40; // [rsp+C8h] [rbp+20h] BYREF

  if ( (a3 & 0xFFFFFFFE) == 0 )
  {
    v4 = a2[1];
    if ( !v4 )
    {
      if ( *a2 )
        return (unsigned int)SkmiRemoveProtectedNormalKernelPage(BugCheckParameter3);
      else
        return (unsigned int)SkmiRemovePlaceholderPage(BugCheckParameter3);
    }
    if ( !a3 )
    {
      if ( v4 == -2 )
        return (unsigned int)-1073741816;
      if ( v4 >= 0xFFFFFFFFFFFFFFF0uLL )
        return (unsigned int)-1073741788;
      if ( (v4 & 0xFFFFFFFEBFFFFFFFuLL) - 1 > 0x3FFFFFE )
        return (unsigned int)-1073741788;
      if ( (0x140000000LL & v4) == 0x40000000 )
        return (unsigned int)-1073741788;
      if ( (0x140000000LL & v4) != 0x140000000LL )
        return (unsigned int)-1073741788;
      v7 = SkobpGlobalHandleTable;
      if ( !SkobpGlobalHandleTable )
        return (unsigned int)-1073741788;
      v8 = *a2;
      v10 = SkobpLockHandleTable(SkobpGlobalHandleTable);
      HandleEntry = (volatile signed __int64 *)SkobpLocateHandleEntry(v7, ((unsigned int)(v9 >> 2) & 0xAFFFFFFF) - 1, 0);
      v12 = HandleEntry;
      if ( HandleEntry )
      {
        _m_prefetchw((const void *)HandleEntry);
LABEL_17:
        v13 = *v12;
        while ( v13 < 0 )
        {
          if ( (((_BYTE)v13 + 1) & 0xF) == 0 )
          {
            _mm_pause();
            goto LABEL_17;
          }
          v14 = v13;
          v15 = _InterlockedCompareExchange64(v12, (v13 + 1) ^ (v13 ^ (v13 + 1)) & 0xFFFFFFFFFFFFFFF0uLL, v13);
          v13 = v15;
          if ( v15 == v14 )
          {
            v16 = v15 & 0xFFFFFFFFFFFFFFF0uLL;
            if ( _InterlockedIncrement64((volatile signed __int64 *)((v15 & 0xFFFFFFFFFFFFFFF0uLL) + 24)) <= 1 )
              __fastfail(0xEu);
            _InterlockedDecrement((volatile signed __int32 *)v12);
            goto LABEL_26;
          }
        }
      }
      v16 = 0;
LABEL_26:
      _m_prefetchw((const void *)(v7 + 6));
      v17 = *(_WORD *)(v7 + 6);
      do
      {
        if ( v17 == 0x8001 )
          __fastfail(0xEu);
        v19 = v17;
        v18 = v17;
        LOWORD(v19) = v17 - 1;
        v17 = _InterlockedCompareExchange16((volatile signed __int16 *)(v7 + 6), v17 - 1, v17);
      }
      while ( v17 != v18 );
      LOBYTE(v19) = v10;
      SkeLowerIrql(v19);
      if ( !v16 )
        return (unsigned int)-1073741816;
      v20 = (_DWORD *)(v16 + 32);
      v21 = v8 >> 12;
      v22 = *(__int64 (__fastcall ***)(ULONG_PTR))(v16 + 16);
      if ( v22 == &SkmiImageType )
      {
        v6 = SkmiInvalidateImagePage(BugCheckParameter3);
LABEL_65:
        SkobDereferenceObject((__int64)v20);
        return v6;
      }
      if ( v22 != (__int64 (__fastcall **)(ULONG_PTR))&SkpsProcessType )
      {
        v6 = -1073741816;
        goto LABEL_65;
      }
      if ( (*v20 & 0x400) != 0 )
      {
        v24 = SkAcquireSpinLockExclusive(v16 + 152);
        v25 = *(__int64 **)(v16 + 136);
        v26 = v24;
        while ( v25 )
        {
          v27 = *((_DWORD *)v25 + 8);
          if ( v21 < (*((unsigned int *)v25 + 6) | ((unsigned __int64)(v27 & 0xFFF) << 32)) )
          {
            v25 = (__int64 *)*v25;
          }
          else
          {
            if ( v21 <= (*((unsigned int *)v25 + 7) | ((unsigned __int64)(v27 & 0xFFF000) << 20)) )
              break;
            v25 = (__int64 *)v25[1];
          }
        }
        if ( v25 )
        {
          v23 = v25 - 67;
          SkobReferenceObject((__int64)(v25 - 67));
        }
        else
        {
          v23 = 0;
        }
        v20[30] = 0;
        SkTrackSpinLockRelease();
        LOBYTE(v28) = v26;
        SkeLowerIrql(v28);
        if ( !v23 )
        {
          v6 = 0;
          goto LABEL_65;
        }
      }
      else
      {
        v23 = (__int64 *)(v16 + 32);
      }
      v38 = 0;
      memset(v39, 0, 32);
      if ( (SkmiFlags & 0x100) == 0 && !KeGetPcr()->NtTib.ExceptionList[6].Handler )
      {
        v6 = -1073741811;
        goto LABEL_61;
      }
      v29 = SkiAttachProcess(v23);
      v30 = SkAcquireSpinLockShared(v23 + 1);
      v31 = 8 * (v21 & 0xFFFFFFFFFLL) - 0x98000000000LL;
      v32 = SkmiPrepareFaultChainForUpdate((__int64)v23, v31, (__int64)&v38, BugCheckParameter3, 0);
      v6 = v32;
      if ( v32 == -1073741819 )
      {
        v6 = 0;
      }
      else if ( v32 >= 0 )
      {
        if ( (v39[0] & 0x800) != 0 )
        {
          if ( BugCheckParameter3 > 0xFFFFFFFFFFLL )
            __fastfail(0x3Fu);
          if ( (*(_QWORD *)(8 * BugCheckParameter3 - 0x180000000000LL) & 0xFFFFFFFFFFFLL) != 0 )
          {
            SKMI_PAGE_SECURITY(328, BugCheckParameter3, 0, 0);
            v6 = -1073741757;
            goto LABEL_60;
          }
          if ( (v39[0] & 0x10) != 0 )
          {
            SkmiSecureZeroPhysicalPage(BugCheckParameter3);
            SkmiReleasePhysicalPage(BugCheckParameter3);
            v40 = 8194;
            SKMI_SWIZZLE_INVALID_PTE(&v40, v34, v35, v36);
            *(_QWORD *)&v39[0] = v40;
          }
          else
          {
            SkmiEncryptPrivatePage(v23, v39);
            SkmiReleasePhysicalPage(BugCheckParameter3);
          }
        }
        SkmiLockFaultChain(v31);
        SkmiCompleteFaultChain(v31, &v38);
      }
LABEL_60:
      LOBYTE(v33) = v30;
      RtlpReleasePropStoreLockShared(v23 + 1, v33);
      SkiAttachProcess(v29);
LABEL_61:
      if ( (*(_DWORD *)v23 & 0x200) != 0 )
        SkobDereferenceObject((__int64)v23);
      goto LABEL_65;
    }
  }
  return 3221225485LL;
}

```

## disassembly

```asm
0x140002a04  push    rbx
0x140002a06  push    rbp
0x140002a07  push    rsi
0x140002a08  push    rdi
0x140002a09  push    r12
0x140002a0b  push    r13
0x140002a0d  push    r14
0x140002a0f  push    r15
0x140002a11  sub     rsp, 68h
0x140002a15  mov     rbp, rcx
0x140002a18  test    r8d, 0FFFFFFFEh
0x140002a1f  jnz     loc_140002E1F
0x140002a25  mov     r10, [rdx+8]
0x140002a29  test    r10, r10
0x140002a2c  jnz     short loc_140002A49
0x140002a2e  mov     rdx, [rdx]
0x140002a31  test    rdx, rdx
0x140002a34  jnz     short loc_140002A3D
0x140002a36  call    SkmiRemovePlaceholderPage
0x140002a3b  jmp     short loc_140002A42
0x140002a3d  call    SkmiRemoveProtectedNormalKernelPage
0x140002a42  mov     ebx, eax
0x140002a44  jmp     loc_140002E1B
0x140002a49  test    r8d, r8d
0x140002a4c  jnz     loc_140002E1F
0x140002a52  cmp     r10, 0FFFFFFFFFFFFFFFEh
0x140002a56  jnz     short loc_140002A62
0x140002a58  mov     ebx, 0C0000008h
0x140002a5d  jmp     loc_140002E1B
0x140002a62  lea     rax, [r10+10h]
0x140002a66  cmp     rax, 10h
0x140002a6a  jb      loc_140002E16
0x140002a70  mov     rax, r10
0x140002a73  mov     rcx, 0FFFFFFFEBFFFFFFFh
0x140002a7d  and     rax, rcx
0x140002a80  mov     r15d, 1
0x140002a86  sub     rax, r15
0x140002a89  cmp     rax, 3FFFFFEh
0x140002a8f  ja      loc_140002E16
0x140002a95  mov     rcx, 140000000h
0x140002a9f  mov     rax, r10
0x140002aa2  and     rax, rcx
0x140002aa5  cmp     rax, 40000000h
0x140002aab  jz      loc_140002E16
0x140002ab1  cmp     rax, rcx
0x140002ab4  jnz     loc_140002E16
0x140002aba  mov     rdi, cs:SkobpGlobalHandleTable
0x140002ac1  test    rdi, rdi
0x140002ac4  jz      loc_140002E16
0x140002aca  mov     r14, [rdx]
0x140002acd  mov     rcx, rdi
0x140002ad0  call    SkobpLockHandleTable
0x140002ad5  shr     r10, 2
0x140002ad9  xor     r8d, r8d
0x140002adc  and     r10d, 0AFFFFFFFh
0x140002ae3  mov     rcx, rdi
0x140002ae6  sub     r10d, r15d
0x140002ae9  mov     sil, al
0x140002aec  mov     edx, r10d
0x140002aef  call    SkobpLocateHandleEntry
0x140002af4  lea     r9d, [r15+0Dh]
0x140002af8  mov     r8, rax
0x140002afb  test    rax, rax
0x140002afe  jz      short loc_140002B57
0x140002b00  prefetchw byte ptr [rax]
0x140002b03  mov     rbx, [r8]
0x140002b06  test    rbx, rbx
0x140002b09  jns     short loc_140002B57
0x140002b0b  lea     rax, [rbx+1]
0x140002b0f  test    al, 0Fh
0x140002b11  jz      short loc_140002B53
0x140002b13  mov     rcx, rax
0x140002b16  mov     rdx, rbx
0x140002b19  xor     rcx, rbx
0x140002b1c  and     rcx, 0FFFFFFFFFFFFFFF0h
0x140002b20  xor     rcx, rax
0x140002b23  mov     rax, rbx
0x140002b26  lock cmpxchg [r8], rcx
0x140002b2b  mov     rbx, rax
0x140002b2e  cmp     rax, rdx
0x140002b31  jnz     short loc_140002B06
0x140002b33  and     rbx, 0FFFFFFFFFFFFFFF0h
0x140002b37  mov     rax, r15
0x140002b3a  lock xadd [rbx+18h], rax
0x140002b40  add     rax, r15
0x140002b43  cmp     rax, r15
0x140002b46  jg      short loc_140002B4D
0x140002b48  mov     rcx, r9
0x140002b4b  int     29h; Win8: RtlFailFast(ecx)
0x140002b4d  lock dec dword ptr [r8]
0x140002b51  jmp     short loc_140002B59
0x140002b53  pause
0x140002b55  jmp     short loc_140002B03
0x140002b57  xor     ebx, ebx
0x140002b59  prefetchw byte ptr [rdi+6]
0x140002b5d  movzx   eax, word ptr [rdi+6]
0x140002b61  mov     ecx, 0FFFF8001h
0x140002b66  cmp     ax, cx
0x140002b69  jz      loc_140002E11
0x140002b6f  movzx   ecx, ax
0x140002b72  movzx   edx, ax
0x140002b75  sub     cx, r15w
0x140002b79  lock cmpxchg [rdi+6], cx
0x140002b7f  cmp     ax, dx
0x140002b82  jnz     short loc_140002B61
0x140002b84  mov     cl, sil
0x140002b87  call    SkeLowerIrql
0x140002b8c  test    rbx, rbx
0x140002b8f  jz      loc_140002A58
0x140002b95  lea     rsi, [rbx+20h]
0x140002b99  shr     r14, 0Ch
0x140002b9d  mov     rax, [rsi-10h]
0x140002ba1  lea     rcx, SkmiImageType
0x140002ba8  cmp     rax, rcx
0x140002bab  jnz     short loc_140002BC2
0x140002bad  mov     r8, r14
0x140002bb0  mov     rdx, rsi
0x140002bb3  mov     rcx, rbp; BugCheckParameter3
0x140002bb6  call    SkmiInvalidateImagePage
0x140002bbb  mov     ebx, eax
0x140002bbd  jmp     loc_140002E07
0x140002bc2  lea     rcx, SkpsProcessType
0x140002bc9  cmp     rax, rcx
0x140002bcc  jnz     loc_140002E02
0x140002bd2  test    dword ptr [rsi], 400h
0x140002bd8  jnz     short loc_140002BE2
0x140002bda  mov     rdi, rsi
0x140002bdd  jmp     loc_140002C69
0x140002be2  lea     rcx, [rsi+78h]
0x140002be6  call    SkAcquireSpinLockExclusive
0x140002beb  mov     r8, [rsi+68h]
0x140002bef  mov     bl, al
0x140002bf1  jmp     short loc_140002C30
0x140002bf3  mov     r9d, [r8+20h]
0x140002bf7  mov     ecx, [r8+18h]
0x140002bfb  mov     edx, r9d
0x140002bfe  and     edx, 0FFFh
0x140002c04  shl     rdx, 20h
0x140002c08  or      rdx, rcx
0x140002c0b  cmp     r14, rdx
0x140002c0e  jb      short loc_140002C2D
0x140002c10  mov     eax, [r8+1Ch]
0x140002c14  and     r9d, 0FFF000h
0x140002c1b  shl     r9, 14h
0x140002c1f  or      r9, rax
0x140002c22  cmp     r14, r9
0x140002c25  jbe     short loc_140002C35
0x140002c27  mov     r8, [r8+8]
0x140002c2b  jmp     short loc_140002C30
0x140002c2d  mov     r8, [r8]
0x140002c30  test    r8, r8
0x140002c33  jnz     short loc_140002BF3
0x140002c35  test    r8, r8
0x140002c38  jnz     short loc_140002C3E
0x140002c3a  xor     edi, edi
0x140002c3c  jmp     short loc_140002C4D
0x140002c3e  lea     rdi, [r8-218h]
0x140002c45  mov     rcx, rdi
0x140002c48  call    SkobReferenceObject
0x140002c4d  mov     dword ptr [rsi+78h], 0
0x140002c54  call    SkTrackSpinLockRelease
0x140002c59  mov     cl, bl
0x140002c5b  call    SkeLowerIrql
0x140002c60  test    rdi, rdi
0x140002c63  jz      loc_140002DFE
0x140002c69  test    cs:SkmiFlags, 100h
0x140002c73  xorps   xmm0, xmm0
0x140002c76  movups  [rsp+0A8h+var_78], xmm0
0x140002c7b  movups  [rsp+0A8h+var_68], xmm0
0x140002c80  movups  [rsp+0A8h+var_58], xmm0
0x140002c85  jnz     short loc_140002CA1
0x140002c87  mov     rax, gs:0
0x140002c90  cmp     qword ptr [rax+68h], 0
0x140002c95  jnz     short loc_140002CA1
0x140002c97  mov     ebx, 0C000000Dh
0x140002c9c  jmp     loc_140002DEC
0x140002ca1  mov     rcx, rdi
0x140002ca4  call    SkiAttachProcess
0x140002ca9  lea     rcx, [rdi+8]
0x140002cad  mov     r12, rax
0x140002cb0  call    SkAcquireSpinLockShared
0x140002cb5  mov     r13b, al
0x140002cb8  mov     rax, 0FFFFFFFFFh
0x140002cc2  and     r14, rax
0x140002cc5  mov     rax, 0FFFFF68000000000h
0x140002ccf  lea     r14, [rax+r14*8]
0x140002cd3  mov     [rsp+0A8h+var_88], 0
0x140002cdb  mov     rdx, r14
0x140002cde  lea     r8, [rsp+0A8h+var_78]
0x140002ce3  mov     r9, rbp
0x140002ce6  mov     rcx, rdi
0x140002ce9  call    SkmiPrepareFaultChainForUpdate
0x140002cee  mov     ebx, eax
0x140002cf0  cmp     eax, 0C0000005h
0x140002cf5  jnz     short loc_140002CFE
0x140002cf7  xor     ebx, ebx
0x140002cf9  jmp     loc_140002DD8
0x140002cfe  test    eax, eax
0x140002d00  js      loc_140002DD8
0x140002d06  test    qword ptr [rsp+0A8h+var_68], 800h
0x140002d0f  jz      loc_140002DC3
0x140002d15  mov     rcx, 0FFFFEFFFFFFFFFFFh
0x140002d1f  mov     rdx, 0FFFFE80000000000h
0x140002d29  mov     rax, rdx
0x140002d2c  sub     rcx, rax
0x140002d2f  sar     rcx, 3
0x140002d33  cmp     rbp, rcx
0x140002d36  jbe     short loc_140002D3F
0x140002d38  mov     ecx, 3Fh ; '?'
0x140002d3d  int     29h; Win8: RtlFailFast(ecx)
0x140002d3f  mov     rax, rdx
0x140002d42  mov     rcx, [rax+rbp*8]
0x140002d46  mov     rax, 0FFFFFFFFFFFh
0x140002d50  test    rax, rcx
0x140002d53  jz      short loc_140002D6F
0x140002d55  xor     r9d, r9d
0x140002d58  xor     r8d, r8d
0x140002d5b  mov     rdx, rbp
0x140002d5e  mov     ecx, 148h
0x140002d63  call    SKMI_PAGE_SECURITY
0x140002d68  mov     ebx, 0C0000043h
0x140002d6d  jmp     short loc_140002DD8
0x140002d6f  test    byte ptr [rsp+0A8h+var_68], 10h
0x140002d74  jnz     short loc_140002D8D
0x140002d76  lea     rdx, [rsp+0A8h+var_68]
0x140002d7b  mov     rcx, rdi
0x140002d7e  call    SkmiEncryptPrivatePage
0x140002d83  mov     rcx, rbp; BugCheckParameter3
0x140002d86  call    SkmiReleasePhysicalPage
0x140002d8b  jmp     short loc_140002DC3
0x140002d8d  mov     rcx, rbp
0x140002d90  call    SkmiSecureZeroPhysicalPage
0x140002d95  mov     rcx, rbp; BugCheckParameter3
0x140002d98  call    SkmiReleasePhysicalPage
0x140002d9d  lea     rcx, [rsp+0A8h+arg_18]
0x140002da5  mov     [rsp+0A8h+arg_18], 2002h
0x140002db1  call    SKMI_SWIZZLE_INVALID_PTE
0x140002db6  mov     r9, [rsp+0A8h+arg_18]
0x140002dbe  mov     qword ptr [rsp+0A8h+var_68], r9
0x140002dc3  mov     rcx, r14
0x140002dc6  call    SkmiLockFaultChain
0x140002dcb  lea     rdx, [rsp+0A8h+var_78]
0x140002dd0  mov     rcx, r14
0x140002dd3  call    SkmiCompleteFaultChain
0x140002dd8  mov     dl, r13b
0x140002ddb  lea     rcx, [rdi+8]
0x140002ddf  call    RtlpReleasePropStoreLockShared
0x140002de4  mov     rcx, r12
0x140002de7  call    SkiAttachProcess
0x140002dec  test    dword ptr [rdi], 200h
0x140002df2  jz      short loc_140002E07
0x140002df4  mov     rcx, rdi
0x140002df7  call    SkobDereferenceObject
0x140002dfc  jmp     short loc_140002E07
0x140002dfe  xor     ebx, ebx
0x140002e00  jmp     short loc_140002E07
0x140002e02  mov     ebx, 0C0000008h
0x140002e07  mov     rcx, rsi
0x140002e0a  call    SkobDereferenceObject
0x140002e0f  jmp     short loc_140002E1B
0x140002e11  mov     rcx, r9
0x140002e14  int     29h; Win8: RtlFailFast(ecx)
0x140002e16  mov     ebx, 0C0000024h
0x140002e1b  mov     eax, ebx
0x140002e1d  jmp     short loc_140002E24
0x140002e1f  mov     eax, 0C000000Dh
0x140002e24  add     rsp, 68h
0x140002e28  pop     r15
0x140002e2a  pop     r14
0x140002e2c  pop     r13
0x140002e2e  pop     r12
0x140002e30  pop     rdi
0x140002e31  pop     rsi
0x140002e32  pop     rbp
0x140002e33  pop     rbx
0x140002e34  retn
```
