# VMX_PLEX_INFO::Associate(VMX_CONFIG_SUMMARY *,uchar)

- ea: `0x14003d9f0`
- end: `0x14003dbb8`
- name: `?Associate@VMX_PLEX_INFO@@UEAAJPEAVVMX_CONFIG_SUMMARY@@E@Z`
- size: `456`
- prototype: `__int64 __fastcall(VMX_PLEX_INFO *this, struct VMX_CONFIG_SUMMARY *, char)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x1400099d8`
- `0x14003d9f0`
- `0x14003f4f8`
- `0x14004037c`

## import_xrefs

- `ntoskrnl!_stricmp` at `0x14003daa3`
- `ntoskrnl!_stricmp` at `0x14003daa3`

## pseudocode

```c
__int64 __fastcall VMX_PLEX_INFO::Associate(VMX_PLEX_INFO *this, struct VMX_CONFIG_SUMMARY *a2, char a3)
{
  unsigned __int64 v4; // rdx
  struct VMX_RECORD *RecordByRecordId; // rax
  VMX_RECORD *v7; // rdi
  VMX_RECORD *v9; // rsi
  VMX_RECORD *v10; // r15
  __int64 v11; // rcx
  VMX_RECORD *v12; // rbp
  __int64 v13; // r13
  unsigned int v14; // edi
  unsigned int v15; // esi

  ++*((_DWORD *)a2 + 1);
  v4 = *((_QWORD *)this + 13);
  if ( !v4 )
    return 0;
  RecordByRecordId = VMX_CONFIG::FindRecordByRecordId(*(VMX_CONFIG **)(*((_QWORD *)this + 6) + 16LL), v4);
  v7 = RecordByRecordId;
  if ( !RecordByRecordId )
  {
    if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x20) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 3), 48, WPP_ecea8329fd353f2ede86956965576228_Traceguids, 3221225485LL);
    }
    return 3221225485LL;
  }
  v9 = 0;
  v10 = 0;
  v11 = *((_QWORD *)RecordByRecordId + (*((_WORD *)RecordByRecordId + 32) & 1) + 5);
  *((_QWORD *)this + 17) = RecordByRecordId;
  v12 = *(VMX_RECORD **)(v11 + 264);
  while ( v12 )
  {
    v13 = *((_QWORD *)v12 + (*((_WORD *)v12 + 32) & 1) + 5);
    if ( _stricmp((const char *)(v13 + 16), (const char *)this + 16) > 0 )
      break;
    v9 = v12;
    v12 = *(VMX_RECORD **)(v13 + 144);
    v10 = v9;
  }
  *((_QWORD *)this + 18) = v12;
  if ( v9 )
  {
    if ( a3 )
    {
      v14 = VMX_RECORD::PreTouch(v9);
      if ( v14 )
      {
        if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x20) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 3), 49, WPP_ecea8329fd353f2ede86956965576228_Traceguids, v14);
        }
        return v14;
      }
    }
    *(_QWORD *)(*((_QWORD *)v10 + (*((_WORD *)v9 + 32) & 1) + 5) + 144LL) = *((_QWORD *)this + 6);
    return 0;
  }
  if ( !a3 || (v15 = VMX_RECORD::PreTouch(v7)) == 0 )
  {
    *(_QWORD *)(*((_QWORD *)v7 + (*((_WORD *)v7 + 32) & 1) + 5) + 264LL) = *((_QWORD *)this + 6);
    return 0;
  }
  if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x20) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 3), 50, WPP_ecea8329fd353f2ede86956965576228_Traceguids, v15);
  }
  return v15;
}

```

## disassembly

```asm
0x14003d9f0  push    rbx
0x14003d9f2  push    rbp
0x14003d9f3  push    rsi
0x14003d9f4  push    rdi
0x14003d9f5  push    r12
0x14003d9f7  push    r13
0x14003d9f9  push    r14
0x14003d9fb  push    r15
0x14003d9fd  sub     rsp, 28h
0x14003da01  inc     dword ptr [rdx+4]
0x14003da04  mov     r14b, r8b
0x14003da07  mov     rdx, [rcx+68h]; unsigned __int64
0x14003da0b  mov     rbx, rcx
0x14003da0e  test    rdx, rdx
0x14003da11  jz      loc_14003DBA4
0x14003da17  mov     rcx, [rcx+30h]
0x14003da1b  mov     rcx, [rcx+10h]; this
0x14003da1f  call    ?FindRecordByRecordId@VMX_CONFIG@@QEAAPEAVVMX_RECORD@@_K@Z; VMX_CONFIG::FindRecordByRecordId(unsigned __int64)
0x14003da24  mov     rdi, rax
0x14003da27  test    rax, rax
0x14003da2a  jnz     short loc_14003DA6E
0x14003da2c  mov     rcx, cs:WPP_GLOBAL_Control
0x14003da33  lea     rax, WPP_GLOBAL_Control
0x14003da3a  mov     ebx, 0C000000Dh
0x14003da3f  cmp     rcx, rax
0x14003da42  jz      short loc_14003DA67
0x14003da44  mov     eax, [rcx+2Ch]
0x14003da47  test    al, 20h
0x14003da49  jz      short loc_14003DA67
0x14003da4b  cmp     byte ptr [rcx+29h], 2
0x14003da4f  jb      short loc_14003DA67
0x14003da51  mov     rcx, [rcx+18h]
0x14003da55  lea     edx, [rdi+30h]
0x14003da58  mov     r9d, ebx
0x14003da5b  lea     r8, WPP_ecea8329fd353f2ede86956965576228_Traceguids
0x14003da62  call    WPP_SF_d
0x14003da67  mov     eax, ebx
0x14003da69  jmp     loc_14003DBA6
0x14003da6e  movzx   eax, word ptr [rax+40h]
0x14003da72  xor     esi, esi
0x14003da74  and     eax, 1
0x14003da77  xor     r15d, r15d
0x14003da7a  mov     rcx, [rdi+rax*8+28h]
0x14003da7f  mov     [rbx+88h], rdi
0x14003da86  mov     rbp, [rcx+108h]
0x14003da8d  jmp     short loc_14003DAC0
0x14003da8f  movzx   eax, word ptr [rbp+40h]
0x14003da93  lea     rdx, [rbx+10h]; Str2
0x14003da97  and     eax, 1
0x14003da9a  mov     r13, [rbp+rax*8+28h]
0x14003da9f  lea     rcx, [r13+10h]; Str1
0x14003daa3  call    cs:__imp__stricmp
0x14003daaa  nop     dword ptr [rax+rax+00h]
0x14003daaf  test    eax, eax
0x14003dab1  jg      short loc_14003DAC5
0x14003dab3  mov     rsi, rbp
0x14003dab6  mov     rbp, [r13+90h]
0x14003dabd  mov     r15, rsi
0x14003dac0  test    rbp, rbp
0x14003dac3  jnz     short loc_14003DA8F
0x14003dac5  mov     [rbx+90h], rbp
0x14003dacc  test    rsi, rsi
0x14003dacf  jz      short loc_14003DB3D
0x14003dad1  test    r14b, r14b
0x14003dad4  jz      short loc_14003DB24
0x14003dad6  mov     rcx, rsi; this
0x14003dad9  call    ?PreTouch@VMX_RECORD@@QEAAJXZ; VMX_RECORD::PreTouch(void)
0x14003dade  mov     edi, eax
0x14003dae0  test    eax, eax
0x14003dae2  jz      short loc_14003DB24
0x14003dae4  mov     rcx, cs:WPP_GLOBAL_Control
0x14003daeb  lea     rax, WPP_GLOBAL_Control
0x14003daf2  cmp     rcx, rax
0x14003daf5  jz      short loc_14003DB1D
0x14003daf7  mov     edx, [rcx+2Ch]
0x14003dafa  test    dl, 20h
0x14003dafd  jz      short loc_14003DB1D
0x14003daff  cmp     byte ptr [rcx+29h], 2
0x14003db03  jb      short loc_14003DB1D
0x14003db05  mov     rcx, [rcx+18h]
0x14003db09  lea     r8, WPP_ecea8329fd353f2ede86956965576228_Traceguids
0x14003db10  mov     edx, 31h ; '1'
0x14003db15  mov     r9d, edi
0x14003db18  call    WPP_SF_d
0x14003db1d  mov     eax, edi
0x14003db1f  jmp     loc_14003DBA6
0x14003db24  movzx   eax, word ptr [rsi+40h]
0x14003db28  and     eax, 1
0x14003db2b  mov     rcx, [r15+rax*8+28h]
0x14003db30  mov     rax, [rbx+30h]
0x14003db34  mov     [rcx+90h], rax
0x14003db3b  jmp     short loc_14003DBA4
0x14003db3d  test    r14b, r14b
0x14003db40  jz      short loc_14003DB8D
0x14003db42  mov     rcx, rdi; this
0x14003db45  call    ?PreTouch@VMX_RECORD@@QEAAJXZ; VMX_RECORD::PreTouch(void)
0x14003db4a  mov     esi, eax
0x14003db4c  test    eax, eax
0x14003db4e  jz      short loc_14003DB8D
0x14003db50  mov     rcx, cs:WPP_GLOBAL_Control
0x14003db57  lea     rax, WPP_GLOBAL_Control
0x14003db5e  cmp     rcx, rax
0x14003db61  jz      short loc_14003DB89
0x14003db63  mov     edx, [rcx+2Ch]
0x14003db66  test    dl, 20h
0x14003db69  jz      short loc_14003DB89
0x14003db6b  cmp     byte ptr [rcx+29h], 2
0x14003db6f  jb      short loc_14003DB89
0x14003db71  mov     rcx, [rcx+18h]
0x14003db75  lea     r8, WPP_ecea8329fd353f2ede86956965576228_Traceguids
0x14003db7c  mov     edx, 32h ; '2'
0x14003db81  mov     r9d, esi
0x14003db84  call    WPP_SF_d
0x14003db89  mov     eax, esi
0x14003db8b  jmp     short loc_14003DBA6
0x14003db8d  movzx   eax, word ptr [rdi+40h]
0x14003db91  and     eax, 1
0x14003db94  mov     rcx, [rdi+rax*8+28h]
0x14003db99  mov     rax, [rbx+30h]
0x14003db9d  mov     [rcx+108h], rax
0x14003dba4  xor     eax, eax
0x14003dba6  add     rsp, 28h
0x14003dbaa  pop     r15
0x14003dbac  pop     r14
0x14003dbae  pop     r13
0x14003dbb0  pop     r12
0x14003dbb2  pop     rdi
0x14003dbb3  pop     rsi
0x14003dbb4  pop     rbp
0x14003dbb5  pop     rbx
0x14003dbb6  retn
```
