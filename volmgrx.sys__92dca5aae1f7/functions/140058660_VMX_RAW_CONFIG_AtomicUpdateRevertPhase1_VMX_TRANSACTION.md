# VMX_RAW_CONFIG::AtomicUpdateRevertPhase1(VMX_TRANSACTION *)

- ea: `0x140058660`
- end: `0x1400587cd`
- name: `?AtomicUpdateRevertPhase1@VMX_RAW_CONFIG@@QEAAXPEAVVMX_TRANSACTION@@@Z`
- size: `365`
- prototype: `void __fastcall(VMX_RAW_CONFIG *__hidden this, struct VMX_TRANSACTION *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14002a3f4`
- `0x14004e3ac`

## callees

- `0x1400097c0`
- `0x140031adc`
- `0x140058660`
- `0x140058efc`
- `0x1400591f0`

## pseudocode

```c
void __fastcall VMX_RAW_CONFIG::AtomicUpdateRevertPhase1(VMX_RAW_CONFIG *this, struct VMX_TRANSACTION *a2)
{
  unsigned __int64 v2; // rdi
  bool v4; // zf
  struct VMX_CHANGE_IDENTITY_TRANSACTION *v5; // rdx
  unsigned __int8 v6; // r9
  VMX_RAW_CONFIG *v7; // rsi
  VMX_RAW_CONFIG *v8; // rdx
  __int16 v9; // ax
  __int64 v10; // rax
  __int128 v11; // xmm0
  __int128 v12; // xmm1

  v2 = (unsigned __int64)a2;
  v4 = *((_WORD *)a2 + 24) == 1;
  *((_WORD *)this + 36) = 4;
  if ( !v4 )
    v2 = 0;
  *((_WORD *)this + 52) |= 1u;
  if ( v2 )
  {
    *(_OWORD *)((char *)this + 8) = *(_OWORD *)(v2 + 64);
    RtlStringCbCopyA((NTSTRSAFE_PSTR)this + 24, 0x20u, (NTSTRSAFE_PCSTR)(v2 + 80));
    v5 = (struct VMX_CHANGE_IDENTITY_TRANSACTION *)v2;
    v6 = 0;
  }
  else
  {
    v5 = 0;
    v6 = 1;
  }
  VMX_RAW_CONFIG::IncrementalWrite(this, v5, 0, v6, 0);
  VMX_RAW_CONFIG::Untouch(this);
  v7 = (VMX_RAW_CONFIG *)*((_QWORD *)this + 14);
  while ( v7 != (VMX_RAW_CONFIG *)((char *)this + 112) )
  {
    v8 = v7;
    v7 = *(VMX_RAW_CONFIG **)v7;
    v9 = *((_WORD *)v8 + 11);
    if ( (v9 & 2) != 0 )
    {
      *((_WORD *)this + 52) |= 2u;
      VMX_RAW_CONFIG::DeleteRawRecord(this, v8);
    }
    else if ( (v9 & 1) != 0 )
    {
      *((_WORD *)this + 52) |= 2u;
      *((_WORD *)v8 + 11) &= ~1u;
      *(_WORD *)(*((_QWORD *)this + 17) + 24LL * *((unsigned int *)v8 + 8) + 20) |= 1u;
      *((_DWORD *)this + 25) -= (*((_DWORD *)this + 20) - 16 + *((_DWORD *)v8 + 7) + 7)
                              / (unsigned int)(*((_DWORD *)this + 20) - 16);
    }
  }
  if ( (*((_BYTE *)this + 104) & 2) != 0 )
  {
    VMX_RAW_CONFIG::IncrementalWrite(
      this,
      (struct VMX_CHANGE_IDENTITY_TRANSACTION *)(v2 & ((unsigned __int128)-(__int128)v2 >> 64)),
      0,
      v2 == 0,
      0);
    VMX_RAW_CONFIG::Untouch(this);
  }
  v10 = *((_QWORD *)this + 7);
  *((_WORD *)this + 52) |= 1u;
  v11 = *((_OWORD *)this + 9);
  *((_QWORD *)this + 8) = v10;
  v12 = *(_OWORD *)((char *)this + 156);
  *((_WORD *)this + 36) = 1;
  *(_OWORD *)((char *)this + 172) = v11;
  *(_OWORD *)((char *)this + 184) = v12;
  VMX_RAW_CONFIG::IncrementalWrite(
    this,
    (struct VMX_CHANGE_IDENTITY_TRANSACTION *)(v2 & ((unsigned __int128)-(__int128)v2 >> 64)),
    0,
    v2 == 0,
    0);
  VMX_RAW_CONFIG::Untouch(this);
}

```

## disassembly

```asm
0x140058660  push    rbx
0x140058662  push    rsi
0x140058663  push    rdi
0x140058664  push    r14
0x140058666  push    r15
0x140058668  sub     rsp, 30h
0x14005866c  xor     eax, eax
0x14005866e  mov     rdi, rdx
0x140058671  mov     rbx, rcx
0x140058674  lea     r15d, [rax+1]
0x140058678  cmp     [rdx+30h], r15w
0x14005867d  mov     word ptr [rcx+48h], 4
0x140058683  cmovnz  rdi, rax
0x140058687  or      [rcx+68h], r15w
0x14005868c  test    rdi, rdi
0x14005868f  jz      short loc_1400586B2
0x140058691  movups  xmm0, xmmword ptr [rdi+40h]
0x140058695  lea     r8, [rdi+50h]; pszSrc
0x140058699  lea     edx, [rax+20h]; cbDest
0x14005869c  movdqu  xmmword ptr [rcx+8], xmm0
0x1400586a1  add     rcx, 18h; pszDest
0x1400586a5  call    RtlStringCbCopyA
0x1400586aa  mov     rdx, rdi
0x1400586ad  xor     r9b, r9b
0x1400586b0  jmp     short loc_1400586B7
0x1400586b2  xor     edx, edx; struct VMX_CHANGE_IDENTITY_TRANSACTION *
0x1400586b4  mov     r9b, r15b; unsigned __int8
0x1400586b7  xor     r8d, r8d; struct VMX_CONFIG_COPY *
0x1400586ba  mov     [rsp+58h+var_38], 0; unsigned __int8
0x1400586bf  mov     rcx, rbx; this
0x1400586c2  call    ?IncrementalWrite@VMX_RAW_CONFIG@@AEAAJPEAVVMX_CHANGE_IDENTITY_TRANSACTION@@PEAVVMX_CONFIG_COPY@@EE@Z; VMX_RAW_CONFIG::IncrementalWrite(VMX_CHANGE_IDENTITY_TRANSACTION *,VMX_CONFIG_COPY *,uchar,uchar)
0x1400586c7  mov     rcx, rbx; this
0x1400586ca  call    ?Untouch@VMX_RAW_CONFIG@@QEAAXXZ; VMX_RAW_CONFIG::Untouch(void)
0x1400586cf  lea     r14, [rbx+70h]
0x1400586d3  mov     rsi, [r14]
0x1400586d6  jmp     short loc_140058731
0x1400586d8  mov     rdx, rsi; struct VMX_RAW_RECORD *
0x1400586db  mov     rsi, [rsi]
0x1400586de  movzx   eax, word ptr [rdx+16h]
0x1400586e2  test    al, 2
0x1400586e4  jz      short loc_1400586F5
0x1400586e6  or      word ptr [rbx+68h], 2
0x1400586eb  mov     rcx, rbx; this
0x1400586ee  call    ?DeleteRawRecord@VMX_RAW_CONFIG@@AEAAXPEAVVMX_RAW_RECORD@@@Z; VMX_RAW_CONFIG::DeleteRawRecord(VMX_RAW_RECORD *)
0x1400586f3  jmp     short loc_140058731
0x1400586f5  test    r15b, al
0x1400586f8  jz      short loc_140058731
0x1400586fa  or      word ptr [rbx+68h], 2
0x1400586ff  mov     eax, 0FFFEh
0x140058704  and     [rdx+16h], ax
0x140058708  mov     eax, [rdx+20h]
0x14005870b  lea     rcx, [rax+rax*2]
0x14005870f  mov     rax, [rbx+88h]
0x140058716  or      [rax+rcx*8+14h], r15w
0x14005871c  mov     eax, [rdx+1Ch]
0x14005871f  xor     edx, edx
0x140058721  mov     ecx, [rbx+50h]
0x140058724  add     eax, 7
0x140058727  add     ecx, 0FFFFFFF0h
0x14005872a  add     eax, ecx
0x14005872c  div     ecx
0x14005872e  sub     [rbx+64h], eax
0x140058731  cmp     rsi, r14
0x140058734  jnz     short loc_1400586D8
0x140058736  test    byte ptr [rbx+68h], 2
0x14005873a  jz      short loc_140058767
0x14005873c  mov     rax, rdi
0x14005873f  mov     [rsp+58h+var_38], 0; unsigned __int8
0x140058744  neg     rax
0x140058747  mov     rcx, rbx; this
0x14005874a  sbb     rdx, rdx
0x14005874d  and     rdx, rdi; struct VMX_CHANGE_IDENTITY_TRANSACTION *
0x140058750  test    rdi, rdi
0x140058753  setz    r9b; unsigned __int8
0x140058757  xor     r8d, r8d; struct VMX_CONFIG_COPY *
0x14005875a  call    ?IncrementalWrite@VMX_RAW_CONFIG@@AEAAJPEAVVMX_CHANGE_IDENTITY_TRANSACTION@@PEAVVMX_CONFIG_COPY@@EE@Z; VMX_RAW_CONFIG::IncrementalWrite(VMX_CHANGE_IDENTITY_TRANSACTION *,VMX_CONFIG_COPY *,uchar,uchar)
0x14005875f  mov     rcx, rbx; this
0x140058762  call    ?Untouch@VMX_RAW_CONFIG@@QEAAXXZ; VMX_RAW_CONFIG::Untouch(void)
0x140058767  mov     rax, [rbx+38h]
0x14005876b  mov     rcx, rbx; this
0x14005876e  or      [rbx+68h], r15w
0x140058773  movups  xmm0, xmmword ptr [rbx+90h]
0x14005877a  mov     [rbx+40h], rax
0x14005877e  mov     rax, rdi
0x140058781  movups  xmm1, xmmword ptr [rbx+9Ch]
0x140058788  neg     rax
0x14005878b  mov     [rbx+48h], r15w
0x140058790  movups  xmmword ptr [rbx+0ACh], xmm0
0x140058797  sbb     rdx, rdx
0x14005879a  mov     [rsp+58h+var_38], 0; unsigned __int8
0x14005879f  and     rdx, rdi; struct VMX_CHANGE_IDENTITY_TRANSACTION *
0x1400587a2  test    rdi, rdi
0x1400587a5  movups  xmmword ptr [rbx+0B8h], xmm1
0x1400587ac  setz    r9b; unsigned __int8
0x1400587b0  xor     r8d, r8d; struct VMX_CONFIG_COPY *
0x1400587b3  call    ?IncrementalWrite@VMX_RAW_CONFIG@@AEAAJPEAVVMX_CHANGE_IDENTITY_TRANSACTION@@PEAVVMX_CONFIG_COPY@@EE@Z; VMX_RAW_CONFIG::IncrementalWrite(VMX_CHANGE_IDENTITY_TRANSACTION *,VMX_CONFIG_COPY *,uchar,uchar)
0x1400587b8  mov     rcx, rbx; this
0x1400587bb  call    ?Untouch@VMX_RAW_CONFIG@@QEAAXXZ; VMX_RAW_CONFIG::Untouch(void)
0x1400587c0  add     rsp, 30h
0x1400587c4  pop     r15
0x1400587c6  pop     r14
0x1400587c8  pop     rdi
0x1400587c9  pop     rsi
0x1400587ca  pop     rbx
0x1400587cb  retn
```
