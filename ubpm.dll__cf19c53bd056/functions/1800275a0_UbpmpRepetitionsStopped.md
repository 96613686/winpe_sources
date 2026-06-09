# UbpmpRepetitionsStopped

- ea: `0x1800275a0`
- end: `0x18002773f`
- name: `UbpmpRepetitionsStopped`
- size: `415`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180007c50`
- `0x180007e30`
- `0x180009fb8`
- `0x18001e9f4`
- `0x1800275a0`
- `0x18003d810`

## import_xrefs

- `ntdll!RtlReleaseSRWLockShared` at `0x180027696`
- `ntdll!RtlReleaseSRWLockShared` at `0x180027696`
- `ntdll!RtlAcquireSRWLockShared` at `0x1800275e4`
- `ntdll!RtlAcquireSRWLockShared` at `0x1800275e4`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x180027672`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x180027672`

## pseudocode

```c
__int64 __fastcall UbpmpRepetitionsStopped(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 result; // rax
  _QWORD *v6; // rax
  _QWORD *v7; // r8
  unsigned __int16 v8; // dx
  unsigned int v9; // r9d
  unsigned int v10; // esi
  unsigned int i; // edi
  __int64 v12; // r14
  __int64 Source1; // [rsp+30h] [rbp-38h] BYREF

  Source1 = a2;
  result = UbpmConsumerIncPendingActions(a3);
  if ( !(_DWORD)result )
  {
    RtlAcquireSRWLockShared(a3 + 48);
    if ( (*(_BYTE *)(a3 + 41) & 1) != 0 )
    {
      v6 = *(_QWORD **)(a3 + 240);
      if ( v6 != (_QWORD *)(a3 + 240) )
      {
        do
        {
          v7 = v6;
          if ( v6[7] == a1 )
            break;
          if ( v6[5] == a1 )
            break;
          v6 = (_QWORD *)*v6;
          v7 = 0;
        }
        while ( v6 != (_QWORD *)(a3 + 240) );
        if ( v7 )
        {
          v8 = 0;
          v9 = *(_DWORD *)(*(_QWORD *)(a3 + 24) + 20LL);
          if ( v9 )
          {
            do
            {
              if ( *(_QWORD *)(*(_QWORD *)(a3 + 32) + 40LL * v8) == v7[4] )
                break;
              ++v8;
            }
            while ( v8 < v9 );
          }
          v10 = v8;
          if ( v8 == v9 )
            __fastfail(0x8000FFFF);
          for ( i = 0; i < 5; ++i )
          {
            v12 = 28LL * i;
            if ( RtlCompareMemory(&Source1, (char *)&g_CSebConditions + v12 + 20, 8u) == 8 )
            {
              UbpmpActionTerminatesOnConstraint(
                (struct _UBPM_TRIGGER_CONSUMER_BLOCK *)a3,
                v10,
                *(_DWORD *)((char *)&g_CSebConditions + v12 + 16));
              break;
            }
          }
        }
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        60,
        (unsigned int)WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids,
        *(_QWORD *)(*(_QWORD *)(a3 + 24) + 8LL),
        199);
    }
    RtlReleaseSRWLockShared(a3 + 48);
    return UbpmConsumerDecPendingActions(a3);
  }
  return result;
}

```

## disassembly

```asm
0x1800275a0  mov     [rsp+arg_0], rbx
0x1800275a5  mov     [rsp+arg_18], rbp
0x1800275aa  push    rsi
0x1800275ab  push    rdi
0x1800275ac  push    r12
0x1800275ae  push    r14
0x1800275b0  push    r15
0x1800275b2  sub     rsp, 40h
0x1800275b6  mov     rax, cs:__security_cookie
0x1800275bd  xor     rax, rsp
0x1800275c0  mov     [rsp+68h+var_30], rax
0x1800275c5  mov     rdi, rcx
0x1800275c8  mov     [rsp+68h+Source1], rdx
0x1800275cd  mov     rcx, r8
0x1800275d0  mov     rbx, r8
0x1800275d3  call    UbpmConsumerIncPendingActions
0x1800275d8  test    eax, eax
0x1800275da  jnz     loc_1800276A4
0x1800275e0  lea     rcx, [rbx+30h]
0x1800275e4  call    cs:__imp_RtlAcquireSRWLockShared
0x1800275ea  mov     r15d, 1
0x1800275f0  test    [rbx+29h], r15b
0x1800275f4  jz      loc_1800276F5
0x1800275fa  lea     rcx, [rbx+0F0h]
0x180027601  mov     rax, [rcx]
0x180027604  cmp     rax, rcx
0x180027607  jz      loc_180027692
0x18002760d  mov     r8, rax
0x180027610  cmp     [rax+38h], rdi
0x180027614  jz      short loc_180027627
0x180027616  cmp     [rax+28h], rdi
0x18002761a  jz      short loc_180027627
0x18002761c  mov     rax, [rax]
0x18002761f  xor     r8d, r8d
0x180027622  cmp     rax, rcx
0x180027625  jnz     short loc_18002760D
0x180027627  test    r8, r8
0x18002762a  jz      short loc_180027692
0x18002762c  mov     rax, [rbx+18h]
0x180027630  xor     edx, edx
0x180027632  mov     r9d, [rax+14h]
0x180027636  test    r9d, r9d
0x180027639  jnz     loc_1800276CA
0x18002763f  movzx   esi, dx
0x180027642  cmp     esi, r9d
0x180027645  jz      loc_180027738
0x18002764b  xor     edi, edi
0x18002764d  lea     r12, ?g_CSebConditions@@3PAU_UBPM_GLOBAL_STATE_CONDITIONS@@A; _UBPM_GLOBAL_STATE_CONDITIONS near * g_CSebConditions
0x180027654  cmp     edi, 5
0x180027657  jnb     short loc_180027692
0x180027659  mov     eax, edi
0x18002765b  lea     rdx, [r12+14h]
0x180027660  imul    r14, rax, 1Ch
0x180027664  mov     r8d, 8; Length
0x18002766a  lea     rcx, [rsp+68h+Source1]; Source1
0x18002766f  add     rdx, r14; Source2
0x180027672  call    cs:__imp_RtlCompareMemory
0x180027678  cmp     rax, 8
0x18002767c  jz      short loc_180027683
0x18002767e  add     edi, r15d
0x180027681  jmp     short loc_180027654
0x180027683  mov     r8d, [r14+r12+10h]; unsigned int
0x180027688  mov     edx, esi; unsigned int
0x18002768a  mov     rcx, rbx; struct _UBPM_TRIGGER_CONSUMER_BLOCK *
0x18002768d  call    UbpmpActionTerminatesOnConstraint
0x180027692  lea     rcx, [rbx+30h]
0x180027696  call    cs:__imp_RtlReleaseSRWLockShared
0x18002769c  mov     rcx, rbx
0x18002769f  call    UbpmConsumerDecPendingActions
0x1800276a4  mov     rcx, [rsp+68h+var_30]
0x1800276a9  xor     rcx, rsp; StackCookie
0x1800276ac  call    __security_check_cookie
0x1800276b1  lea     r11, [rsp+68h+var_28]
0x1800276b6  mov     rbx, [r11+30h]
0x1800276ba  mov     rbp, [r11+48h]
0x1800276be  mov     rsp, r11
0x1800276c1  pop     r15
0x1800276c3  pop     r14
0x1800276c5  pop     r12
0x1800276c7  pop     rdi
0x1800276c8  pop     rsi
0x1800276c9  retn
0x1800276ca  mov     r10, [r8+20h]
0x1800276ce  mov     r8, [rbx+20h]
0x1800276d2  movzx   eax, dx
0x1800276d5  lea     rcx, [rax+rax*4]
0x1800276d9  cmp     [r8+rcx*8], r10
0x1800276dd  jz      loc_18002763F
0x1800276e3  add     dx, r15w
0x1800276e7  movzx   eax, dx
0x1800276ea  cmp     eax, r9d
0x1800276ed  jnb     loc_18002763F
0x1800276f3  jmp     short loc_1800276D2
0x1800276f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800276fc  lea     rax, WPP_GLOBAL_Control
0x180027703  cmp     rcx, rax
0x180027706  jz      short loc_180027692
0x180027708  test    [rcx+1Ch], r15b
0x18002770c  jz      short loc_180027692
0x18002770e  mov     r9, [rbx+18h]
0x180027712  lea     r8, WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids
0x180027719  mov     rcx, [rcx+10h]
0x18002771d  mov     edx, 3Ch ; '<'
0x180027722  mov     [rsp+68h+var_48], 4C7h
0x18002772a  mov     r9, [r9+8]
0x18002772e  call    WPP_SF_Sd
0x180027733  jmp     loc_180027692
0x180027738  mov     ecx, 8000FFFFh
0x18002773d  int     29h; Win8: RtlFailFast(ecx)
```
