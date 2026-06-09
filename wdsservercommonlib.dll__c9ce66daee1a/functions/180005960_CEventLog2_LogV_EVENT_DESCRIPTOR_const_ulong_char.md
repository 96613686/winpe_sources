# CEventLog2::LogV(_EVENT_DESCRIPTOR const *,ulong,char *)

- ea: `0x180005960`
- end: `0x180005a83`
- name: `?LogV@CEventLog2@@QEAAKPEBU_EVENT_DESCRIPTOR@@KPEAD@Z`
- size: `291`
- prototype: `unsigned int(CEventLog2 *__hidden this, const struct _EVENT_DESCRIPTOR *, unsigned int, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180005930`

## callees

- `0x18000179c`
- `0x180005960`
- `0x180005ac4`
- `0x18002e468`

## import_xrefs

- `ADVAPI32!EventWrite` at `0x180005a3b`
- `ADVAPI32!EventWrite` at `0x180005a3b`

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
0x180005960  mov     rax, rsp
0x180005963  mov     [rax+8], rbx
0x180005967  mov     [rax+18h], rbp
0x18000596b  mov     [rax+20h], rsi
0x18000596f  mov     [rax+10h], rdx
0x180005973  push    rdi
0x180005974  push    r12
0x180005976  push    r13
0x180005978  push    r14
0x18000597a  push    r15
0x18000597c  sub     rsp, 20h
0x180005980  xor     esi, esi
0x180005982  mov     ebp, r8d
0x180005985  xor     r15d, r15d
0x180005988  xor     r12d, r12d
0x18000598b  mov     rdi, r9
0x18000598e  mov     r13, rcx
0x180005991  cmp     [rcx+8], esi
0x180005994  jnz     short loc_18000599E
0x180005996  lea     ebx, [rsi+32h]
0x180005999  jmp     loc_180005A63
0x18000599e  mov     r14, rbp
0x1800059a1  test    r8d, r8d
0x1800059a4  jz      loc_180005A2C
0x1800059aa  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800059b1  mov     eax, 10h
0x1800059b6  mul     r14
0x1800059b9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800059c0  cmovo   rax, rcx
0x1800059c4  mov     rcx, rax; unsigned __int64
0x1800059c7  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800059cc  mov     rsi, rax
0x1800059cf  test    rax, rax
0x1800059d2  jnz     short loc_1800059DC
0x1800059d4  lea     ebx, [rax+8]
0x1800059d7  jmp     loc_180005A63
0x1800059dc  test    ebp, ebp
0x1800059de  jz      short loc_180005A2C
0x1800059e0  lea     r8, [rax+0Ch]
0x1800059e4  mov     ebx, 8
0x1800059e9  mov     edx, [rdi]
0x1800059eb  add     rdi, rbx
0x1800059ee  test    edx, edx
0x1800059f0  jz      short loc_180005A0B
0x1800059f2  sub     edx, 1
0x1800059f5  jz      short loc_180005A0B
0x1800059f7  sub     edx, 1
0x1800059fa  jz      short loc_180005A0B
0x1800059fc  sub     edx, 1
0x1800059ff  jz      short loc_180005A0B
0x180005a01  sub     edx, 1
0x180005a04  jz      short loc_180005A0B
0x180005a06  cmp     edx, 1
0x180005a09  jnz     short loc_180005A16
0x180005a0b  mov     r15d, [rdi]
0x180005a0e  add     rdi, 10h
0x180005a12  mov     r12, [rdi-8]
0x180005a16  and     dword ptr [r8], 0
0x180005a1a  mov     [r8-0Ch], r12
0x180005a1e  mov     [r8-4], r15d
0x180005a22  add     r8, 10h
0x180005a26  sub     r14, 1
0x180005a2a  jnz     short loc_1800059E9
0x180005a2c  mov     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x180005a31  mov     r9, rsi; UserData
0x180005a34  mov     rcx, [r13+0]; RegHandle
0x180005a38  mov     r8d, ebp; UserDataCount
0x180005a3b  call    cs:__imp_EventWrite
0x180005a42  nop     dword ptr [rax+rax+00h]
0x180005a47  mov     ecx, eax
0x180005a49  mov     r9d, 114h
0x180005a4f  mov     ebx, eax
0x180005a51  call    ElValidateWin32_0
0x180005a56  test    rsi, rsi
0x180005a59  jz      short loc_180005A63
0x180005a5b  mov     rcx, rsi; lpMem
0x180005a5e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180005a63  mov     rbp, [rsp+48h+arg_10]
0x180005a68  mov     eax, ebx
0x180005a6a  mov     rbx, [rsp+48h+arg_0]
0x180005a6f  mov     rsi, [rsp+48h+arg_18]
0x180005a74  add     rsp, 20h
0x180005a78  pop     r15
0x180005a7a  pop     r14
0x180005a7c  pop     r13
0x180005a7e  pop     r12
0x180005a80  pop     rdi
0x180005a81  retn
```
