# VMX_RAW_CONFIG::AtomicUpdatePhase3(VMX_TRANSACTION *)

- ea: `0x140058518`
- end: `0x140058659`
- name: `?AtomicUpdatePhase3@VMX_RAW_CONFIG@@QEAAXPEAVVMX_TRANSACTION@@@Z`
- size: `321`
- prototype: `void __fastcall(VMX_RAW_CONFIG *__hidden this, struct VMX_TRANSACTION *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14002a3f4`
- `0x14004e3ac`

## callees

- `0x140031adc`
- `0x140058518`
- `0x140058efc`
- `0x1400591f0`

## pseudocode

```c
void __fastcall VMX_RAW_CONFIG::AtomicUpdatePhase3(VMX_RAW_CONFIG *this, struct VMX_TRANSACTION *a2)
{
  char *v2; // r14
  char *v3; // rsi
  unsigned __int64 v4; // rdi
  char *v6; // r8
  __int16 v7; // ax
  __int64 v8; // rax
  __int128 v9; // xmm0
  __int128 v10; // xmm1

  v2 = (char *)this + 112;
  v3 = (char *)*((_QWORD *)this + 14);
  v4 = (unsigned __int64)a2;
  if ( *((_WORD *)a2 + 24) != 1 )
    v4 = 0;
  while ( v3 != v2 )
  {
    v6 = v3;
    v3 = *(char **)v3;
    v7 = *((_WORD *)v6 + 11);
    if ( (v7 & 2) != 0 )
    {
      *((_WORD *)this + 52) |= 2u;
      *((_WORD *)v6 + 11) &= ~2u;
      *(_WORD *)(*((_QWORD *)this + 17) + 24LL * *((unsigned int *)v6 + 8) + 20) |= 1u;
    }
    else if ( (v7 & 1) != 0 )
    {
      *((_WORD *)this + 52) |= 2u;
      *((_WORD *)v6 + 11) &= ~1u;
      *(_WORD *)(*((_QWORD *)this + 17) + 24LL * *((unsigned int *)v6 + 8) + 20) |= 1u;
      *((_DWORD *)this + 25) -= (*((_DWORD *)this + 20) - 16 + *((_DWORD *)v6 + 7) + 7)
                              / (unsigned int)(*((_DWORD *)this + 20) - 16);
      VMX_RAW_CONFIG::DeleteRawRecord(this, (struct VMX_RAW_RECORD *)v6);
    }
  }
  if ( (*((_BYTE *)this + 104) & 2) != 0 )
  {
    VMX_RAW_CONFIG::IncrementalWrite(
      this,
      (struct VMX_CHANGE_IDENTITY_TRANSACTION *)(v4 & ((unsigned __int128)-(__int128)v4 >> 64)),
      0,
      v4 == 0,
      v4 == 0);
    VMX_RAW_CONFIG::Untouch(this);
  }
  v8 = *((_QWORD *)this + 8);
  *((_WORD *)this + 52) |= 1u;
  v9 = *(_OWORD *)((char *)this + 172);
  *((_QWORD *)this + 7) = v8;
  v10 = *(_OWORD *)((char *)this + 184);
  *((_WORD *)this + 36) = 1;
  *((_OWORD *)this + 9) = v9;
  *(_OWORD *)((char *)this + 156) = v10;
  VMX_RAW_CONFIG::IncrementalWrite(
    this,
    (struct VMX_CHANGE_IDENTITY_TRANSACTION *)(v4 & ((unsigned __int128)-(__int128)v4 >> 64)),
    0,
    v4 == 0,
    v4 == 0);
  VMX_RAW_CONFIG::Untouch(this);
}

```

## disassembly

```asm
0x140058518  push    rbx
0x14005851a  push    rbp
0x14005851b  push    rsi
0x14005851c  push    rdi
0x14005851d  push    r14
0x14005851f  sub     rsp, 30h
0x140058523  xor     eax, eax
0x140058525  lea     r14, [rcx+70h]
0x140058529  mov     rsi, [r14]
0x14005852c  mov     rdi, rdx
0x14005852f  mov     rbx, rcx
0x140058532  lea     ebp, [rax+1]
0x140058535  cmp     [rdx+30h], bp
0x140058539  cmovnz  rdi, rax
0x14005853d  jmp     short loc_1400585BC
0x14005853f  mov     r8, rsi
0x140058542  mov     rsi, [rsi]
0x140058545  movzx   eax, word ptr [r8+16h]
0x14005854a  test    al, 2
0x14005854c  jz      short loc_140058573
0x14005854e  or      word ptr [rbx+68h], 2
0x140058553  mov     eax, 0FFFDh
0x140058558  and     [r8+16h], ax
0x14005855d  mov     eax, [r8+20h]
0x140058561  lea     rcx, [rax+rax*2]
0x140058565  mov     rax, [rbx+88h]
0x14005856c  or      [rax+rcx*8+14h], bp
0x140058571  jmp     short loc_1400585BC
0x140058573  test    bpl, al
0x140058576  jz      short loc_1400585BC
0x140058578  or      word ptr [rbx+68h], 2
0x14005857d  xor     edx, edx
0x14005857f  mov     eax, 0FFFEh
0x140058584  and     [r8+16h], ax
0x140058589  mov     eax, [r8+20h]
0x14005858d  lea     rcx, [rax+rax*2]
0x140058591  mov     rax, [rbx+88h]
0x140058598  or      [rax+rcx*8+14h], bp
0x14005859d  mov     ecx, [rbx+50h]
0x1400585a0  mov     eax, [r8+1Ch]
0x1400585a4  add     ecx, 0FFFFFFF0h
0x1400585a7  add     eax, 7
0x1400585aa  add     eax, ecx
0x1400585ac  div     ecx
0x1400585ae  mov     rdx, r8; struct VMX_RAW_RECORD *
0x1400585b1  mov     rcx, rbx; this
0x1400585b4  sub     [rbx+64h], eax
0x1400585b7  call    ?DeleteRawRecord@VMX_RAW_CONFIG@@AEAAXPEAVVMX_RAW_RECORD@@@Z; VMX_RAW_CONFIG::DeleteRawRecord(VMX_RAW_RECORD *)
0x1400585bc  cmp     rsi, r14
0x1400585bf  jnz     loc_14005853F
0x1400585c5  test    byte ptr [rbx+68h], 2
0x1400585c9  jz      short loc_1400585F6
0x1400585cb  mov     rax, rdi
0x1400585ce  mov     rcx, rbx; this
0x1400585d1  neg     rax
0x1400585d4  sbb     rdx, rdx
0x1400585d7  and     rdx, rdi; struct VMX_CHANGE_IDENTITY_TRANSACTION *
0x1400585da  test    rdi, rdi
0x1400585dd  setz    r9b; unsigned __int8
0x1400585e1  xor     r8d, r8d; struct VMX_CONFIG_COPY *
0x1400585e4  mov     [rsp+58h+var_38], r9b; unsigned __int8
0x1400585e9  call    ?IncrementalWrite@VMX_RAW_CONFIG@@AEAAJPEAVVMX_CHANGE_IDENTITY_TRANSACTION@@PEAVVMX_CONFIG_COPY@@EE@Z; VMX_RAW_CONFIG::IncrementalWrite(VMX_CHANGE_IDENTITY_TRANSACTION *,VMX_CONFIG_COPY *,uchar,uchar)
0x1400585ee  mov     rcx, rbx; this
0x1400585f1  call    ?Untouch@VMX_RAW_CONFIG@@QEAAXXZ; VMX_RAW_CONFIG::Untouch(void)
0x1400585f6  mov     rax, [rbx+40h]
0x1400585fa  mov     rcx, rbx; this
0x1400585fd  or      [rbx+68h], bp
0x140058601  movups  xmm0, xmmword ptr [rbx+0ACh]
0x140058608  mov     [rbx+38h], rax
0x14005860c  mov     rax, rdi
0x14005860f  movups  xmm1, xmmword ptr [rbx+0B8h]
0x140058616  neg     rax
0x140058619  mov     [rbx+48h], bp
0x14005861d  movups  xmmword ptr [rbx+90h], xmm0
0x140058624  sbb     rdx, rdx
0x140058627  and     rdx, rdi; struct VMX_CHANGE_IDENTITY_TRANSACTION *
0x14005862a  test    rdi, rdi
0x14005862d  movups  xmmword ptr [rbx+9Ch], xmm1
0x140058634  setz    r9b; unsigned __int8
0x140058638  xor     r8d, r8d; struct VMX_CONFIG_COPY *
0x14005863b  mov     [rsp+58h+var_38], r9b; unsigned __int8
0x140058640  call    ?IncrementalWrite@VMX_RAW_CONFIG@@AEAAJPEAVVMX_CHANGE_IDENTITY_TRANSACTION@@PEAVVMX_CONFIG_COPY@@EE@Z; VMX_RAW_CONFIG::IncrementalWrite(VMX_CHANGE_IDENTITY_TRANSACTION *,VMX_CONFIG_COPY *,uchar,uchar)
0x140058645  mov     rcx, rbx; this
0x140058648  call    ?Untouch@VMX_RAW_CONFIG@@QEAAXXZ; VMX_RAW_CONFIG::Untouch(void)
0x14005864d  add     rsp, 30h
0x140058651  pop     r14
0x140058653  pop     rdi
0x140058654  pop     rsi
0x140058655  pop     rbp
0x140058656  pop     rbx
0x140058657  retn
```
