# CWdsTptMgmtClient::CreateInstance(ushort const *,CWdsTptMgmtClient * *)

- ea: `0x18001a47c`
- end: `0x18001a55e`
- name: `?CreateInstance@CWdsTptMgmtClient@@SAJPEBGPEAPEAV1@@Z`
- size: `226`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct CWdsTptMgmtClient **)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180008c10`
- `0x18001028c`
- `0x180019974`

## callees

- `0x1800029b8`
- `0x18001a47c`
- `0x18001c3e0`
- `0x180020010`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x18001a4c0`
- `KERNEL32!InitializeCriticalSection` at `0x18001a4c0`
- `WDSCSL!WdsClientInitializeLibrary` at `0x18001a4e6`
- `WDSCSL!WdsClientInitializeLibrary` at `0x18001a4e6`

## pseudocode

```c
__int64 __fastcall CWdsTptMgmtClient::CreateInstance(const unsigned __int16 *a1, struct CWdsTptMgmtClient **a2)
{
  char *v3; // rax
  char *v4; // rdi
  __int64 v5; // rdx
  __int64 v6; // r8
  unsigned int v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // r8

  v3 = (char *)operator new(0x58u, (const struct std::nothrow_t *)&std::nothrow);
  v4 = v3;
  if ( !v3 )
  {
    LOWORD(v7) = 8;
    return (unsigned __int16)v7 | 0x80070000;
  }
  *((_DWORD *)v3 + 2) = 1;
  *(_QWORD *)v3 = &CWdsTptMgmtClient::`vftable';
  InitializeCriticalSection((LPCRITICAL_SECTION)(v3 + 16));
  *((_DWORD *)v4 + 20) = 0;
  v7 = 0;
  *((_QWORD *)v4 + 8) = 0;
  *((_QWORD *)v4 + 9) = 0;
  *((_QWORD *)v4 + 7) = 0;
  if ( !*((_DWORD *)v4 + 20) )
  {
    v7 = WdsClientInitializeLibrary();
    *((_DWORD *)v4 + 20) = v7 == 0;
  }
  ElValidateWin32_14(v7, v5, v6, 117);
  if ( !(unsigned int)ElValidateWin32_14(v7, v8, v9, 1618) )
    *a2 = (struct CWdsTptMgmtClient *)v4;
  if ( v7 )
  {
    (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v4 + 16LL))(v4, 1);
    if ( (int)v7 > 0 )
      return (unsigned __int16)v7 | 0x80070000;
  }
  return v7;
}

```

## disassembly

```asm
0x18001a47c  mov     [rsp+arg_0], rbx
0x18001a481  mov     [rsp+arg_8], rsi
0x18001a486  push    rdi
0x18001a487  sub     rsp, 20h
0x18001a48b  mov     rsi, rdx
0x18001a48e  mov     ecx, 58h ; 'X'; unsigned __int64
0x18001a493  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001a49a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001a49f  mov     rdi, rax
0x18001a4a2  test    rax, rax
0x18001a4a5  jz      loc_18001A53D
0x18001a4ab  mov     dword ptr [rax+8], 1
0x18001a4b2  lea     rcx, [rdi+10h]; lpCriticalSection
0x18001a4b6  lea     rax, ??_7CWdsTptMgmtClient@@6B@; const CWdsTptMgmtClient::`vftable'
0x18001a4bd  mov     [rdi], rax
0x18001a4c0  call    cs:__imp_InitializeCriticalSection
0x18001a4c7  nop     dword ptr [rax+rax+00h]
0x18001a4cc  and     dword ptr [rdi+50h], 0
0x18001a4d0  xor     ebx, ebx
0x18001a4d2  and     qword ptr [rdi+40h], 0
0x18001a4d7  and     qword ptr [rdi+48h], 0
0x18001a4dc  and     qword ptr [rdi+38h], 0
0x18001a4e1  cmp     [rdi+50h], ebx
0x18001a4e4  jnz     short loc_18001A4FE
0x18001a4e6  call    cs:__imp_WdsClientInitializeLibrary
0x18001a4ed  nop     dword ptr [rax+rax+00h]
0x18001a4f2  xor     ecx, ecx
0x18001a4f4  mov     ebx, eax
0x18001a4f6  test    eax, eax
0x18001a4f8  setz    cl
0x18001a4fb  mov     [rdi+50h], ecx
0x18001a4fe  mov     r9d, 75h ; 'u'
0x18001a504  mov     ecx, ebx
0x18001a506  call    ElValidateWin32_14
0x18001a50b  mov     r9d, 652h
0x18001a511  mov     ecx, ebx
0x18001a513  call    ElValidateWin32_14
0x18001a518  test    eax, eax
0x18001a51a  jnz     short loc_18001A51F
0x18001a51c  mov     [rsi], rdi
0x18001a51f  test    ebx, ebx
0x18001a521  jz      short loc_18001A54B
0x18001a523  mov     rax, [rdi]
0x18001a526  mov     edx, 1
0x18001a52b  mov     rcx, rdi
0x18001a52e  mov     rax, [rax+10h]
0x18001a532  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a537  test    ebx, ebx
0x18001a539  jg      short loc_18001A542
0x18001a53b  jmp     short loc_18001A54B
0x18001a53d  mov     ebx, 8
0x18001a542  movzx   ebx, bx
0x18001a545  or      ebx, 80070000h
0x18001a54b  mov     rsi, [rsp+28h+arg_8]
0x18001a550  mov     eax, ebx
0x18001a552  mov     rbx, [rsp+28h+arg_0]
0x18001a557  add     rsp, 20h
0x18001a55b  pop     rdi
0x18001a55c  retn
```
