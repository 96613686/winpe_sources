# CEventLog2::LogV(_EVENT_DESCRIPTOR const *,ulong,char *)

- ea: `0x180006440`
- end: `0x18000656a`
- name: `?LogV@CEventLog2@@QEAAKPEBU_EVENT_DESCRIPTOR@@KPEAD@Z`
- size: `298`
- prototype: `unsigned int(CEventLog2 *__hidden this, const struct _EVENT_DESCRIPTOR *, unsigned int, char *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180006410`

## callees

- `0x18000214c`
- `0x180006440`
- `0x1800065a4`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000653e`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000653e`
- `ADVAPI32!EventWrite` at `0x18000651b`
- `ADVAPI32!EventWrite` at `0x18000651b`

## pseudocode

```c
__int64 __fastcall CEventLog2::LogV(REGHANDLE *this, const struct _EVENT_DESCRIPTOR *a2, ULONG a3, char *a4)
{
  struct _EVENT_DATA_DESCRIPTOR *v4; // rsi
  ULONG v6; // r15d
  __int64 v7; // r12
  __int64 v10; // rbx
  __int64 v11; // r14
  unsigned __int64 v12; // rax
  struct _EVENT_DATA_DESCRIPTOR *v13; // rax
  union _EVENT_DATA_DESCRIPTOR::$535316677C6A15A6ECBA40D88E1D787B *p_Reserved; // r8
  int v15; // edx
  int v16; // edx
  int v17; // edx
  int v18; // edx
  __int64 v19; // rdx
  __int64 v20; // r8

  v4 = 0;
  v6 = 0;
  v7 = 0;
  if ( *((_DWORD *)this + 2) )
  {
    v11 = a3;
    if ( a3 )
    {
      v12 = 16LL * a3;
      if ( !is_mul_ok(a3, 0x10u) )
        v12 = -1;
      v13 = (struct _EVENT_DATA_DESCRIPTOR *)operator new[](v12, (const struct std::nothrow_t *)&std::nothrow);
      v4 = v13;
      if ( !v13 )
      {
        LODWORD(v10) = 8;
        return (unsigned int)v10;
      }
      if ( a3 )
      {
        p_Reserved = (union _EVENT_DATA_DESCRIPTOR::$535316677C6A15A6ECBA40D88E1D787B *)&v13->Reserved;
        do
        {
          v15 = *(_DWORD *)a4;
          a4 += 8;
          if ( !v15
            || (v16 = v15 - 1) == 0
            || (v17 = v16 - 1) == 0
            || (v18 = v17 - 1) == 0
            || (unsigned int)(v18 - 1) <= 1 )
          {
            v6 = *(_DWORD *)a4;
            a4 += 16;
            v7 = *((_QWORD *)a4 - 1);
          }
          p_Reserved->Reserved = 0;
          *(_QWORD *)&p_Reserved[-3].Reserved = v7;
          p_Reserved[-1].Reserved = v6;
          p_Reserved += 4;
          --v11;
        }
        while ( v11 );
      }
    }
    v10 = EventWrite(*this, a2, a3, v4);
    ElValidateWin32_0(v10, v19, v20, 276);
    if ( v4 )
      operator delete(v4);
  }
  else
  {
    LODWORD(v10) = 50;
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180006440  mov     rax, rsp
0x180006443  mov     [rax+8], rbx
0x180006447  mov     [rax+18h], rbp
0x18000644b  mov     [rax+20h], rsi
0x18000644f  mov     [rax+10h], rdx
0x180006453  push    rdi
0x180006454  push    r12
0x180006456  push    r13
0x180006458  push    r14
0x18000645a  push    r15
0x18000645c  sub     rsp, 20h
0x180006460  xor     esi, esi
0x180006462  mov     ebp, r8d
0x180006465  xor     r15d, r15d
0x180006468  xor     r12d, r12d
0x18000646b  mov     rdi, r9
0x18000646e  mov     r13, rcx
0x180006471  cmp     [rcx+8], esi
0x180006474  jnz     short loc_18000647E
0x180006476  lea     ebx, [rsi+32h]
0x180006479  jmp     loc_18000654A
0x18000647e  mov     r14, rbp
0x180006481  test    r8d, r8d
0x180006484  jz      loc_18000650C
0x18000648a  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180006491  mov     eax, 10h
0x180006496  mul     r14
0x180006499  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800064a0  cmovo   rax, rcx
0x1800064a4  mov     rcx, rax; unsigned __int64
0x1800064a7  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800064ac  mov     rsi, rax
0x1800064af  test    rax, rax
0x1800064b2  jnz     short loc_1800064BC
0x1800064b4  lea     ebx, [rax+8]
0x1800064b7  jmp     loc_18000654A
0x1800064bc  test    ebp, ebp
0x1800064be  jz      short loc_18000650C
0x1800064c0  lea     r8, [rax+0Ch]
0x1800064c4  mov     ebx, 8
0x1800064c9  mov     edx, [rdi]
0x1800064cb  add     rdi, rbx
0x1800064ce  test    edx, edx
0x1800064d0  jz      short loc_1800064EB
0x1800064d2  sub     edx, 1
0x1800064d5  jz      short loc_1800064EB
0x1800064d7  sub     edx, 1
0x1800064da  jz      short loc_1800064EB
0x1800064dc  sub     edx, 1
0x1800064df  jz      short loc_1800064EB
0x1800064e1  sub     edx, 1
0x1800064e4  jz      short loc_1800064EB
0x1800064e6  cmp     edx, 1
0x1800064e9  jnz     short loc_1800064F6
0x1800064eb  mov     r15d, [rdi]
0x1800064ee  add     rdi, 10h
0x1800064f2  mov     r12, [rdi-8]
0x1800064f6  and     dword ptr [r8], 0
0x1800064fa  mov     [r8-0Ch], r12
0x1800064fe  mov     [r8-4], r15d
0x180006502  add     r8, 10h
0x180006506  sub     r14, 1
0x18000650a  jnz     short loc_1800064C9
0x18000650c  mov     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x180006511  mov     r9, rsi; UserData
0x180006514  mov     rcx, [r13+0]; RegHandle
0x180006518  mov     r8d, ebp; UserDataCount
0x18000651b  call    cs:__imp_EventWrite
0x180006522  nop     dword ptr [rax+rax+00h]
0x180006527  mov     ecx, eax
0x180006529  mov     r9d, 114h
0x18000652f  mov     ebx, eax
0x180006531  call    ElValidateWin32_0
0x180006536  test    rsi, rsi
0x180006539  jz      short loc_18000654A
0x18000653b  mov     rcx, rsi
0x18000653e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180006545  nop     dword ptr [rax+rax+00h]
0x18000654a  mov     rbp, [rsp+48h+arg_10]
0x18000654f  mov     eax, ebx
0x180006551  mov     rbx, [rsp+48h+arg_0]
0x180006556  mov     rsi, [rsp+48h+arg_18]
0x18000655b  add     rsp, 20h
0x18000655f  pop     r15
0x180006561  pop     r14
0x180006563  pop     r13
0x180006565  pop     r12
0x180006567  pop     rdi
0x180006568  retn
```
