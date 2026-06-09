# _lambda_6d29b35e36e5bb6c3c59788efe28ffe7_$_ResumeCoro$1::operator()

- ea: `0x18000f2d0`
- end: `0x18000f520`
- name: `_lambda_6d29b35e36e5bb6c3c59788efe28ffe7_$_ResumeCoro$1::operator()`
- size: `592`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, loader_planting, service_task`

## callees

- `0x180004144`
- `0x180004534`
- `0x180005dd0`
- `0x1800074e0`
- `0x18000dbd8`
- `0x18000e5a0`
- `0x18000f2d0`
- `0x18001c7e0`
- `0x18001c924`
- `0x180034010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x18000f45e`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x18000f45e`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18000f3b1`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18000f3b1`

## string_xrefs

- `0x18000f424`: `onecore\vm\dv\storage\plan9\dll\p9await.h`
- `0x18000f49c`: `onecore\vm\dv\storage\plan9\dll\p9await.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall lambda_6d29b35e36e5bb6c3c59788efe28ffe7___ResumeCoro_1::operator()(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  char *v5; // rax
  __int64 v6; // rbx
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // r8
  const char *v10; // r9
  __int64 v11; // rax
  const struct std::exception_ptr *v12; // rbx
  __int64 v13; // rdx
  const char *v14; // r9
  __int64 v15; // rcx
  __int64 v16; // rax
  __int64 v17; // [rsp+20h] [rbp-C8h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

  switch ( *((_WORD *)a1 + 4) )
  {
    case 0xFFFF:
    case 3:
      goto LABEL_16;
    case 2:
      v5 = (char *)operator new(0xA40u) + 32;
      a1[3] = v5;
      *((_QWORD *)v5 + 323) = a1 + 340;
      *(_QWORD *)a1[3] = lambda_14a7a5d5c2db807f1a68f78f3c68b6c0___ResumeCoro_1::operator();
      *(_DWORD *)(a1[3] + 8LL) = 65538;
      v6 = a1[3];
      *(_OWORD *)(v6 - 32) = 0;
      *(_OWORD *)(v6 - 16) = 0;
      v17 = a1[3];
      *(_QWORD *)(v17 - 32) = 0;
      *(_BYTE *)(v17 - 24) = 0;
      v7 = (_QWORD *)(v17 - 16);
      *v7 = 0;
      v7[1] = 0;
      __ExceptionPtrCreate((void *)(v17 - 16));
      a1[2] = v6;
      *(_BYTE *)(a1[3] + 2576LL) = 0;
      lambda_14a7a5d5c2db807f1a68f78f3c68b6c0___ResumeCoro_1::operator()(a1[3], v8, v9, v10);
      if ( !*(_BYTE *)(a1[2] - 24LL) )
      {
        *((_WORD *)a1 + 4) = 4;
        if ( (unsigned __int8)p9fs::Task<void>::await_suspend(a1 + 2, a1) )
          return;
      }
      goto LABEL_10;
    case 4:
LABEL_10:
      v12 = (const struct std::exception_ptr *)(a1[2] - 16LL);
      if ( __ExceptionPtrToBool(v12) )
      {
        v15 = std::exception_ptr::exception_ptr((std::exception_ptr *)(a1 + 336), v12);
        std::rethrow_exception(v15);
      }
      v16 = a1[2];
      if ( v16 )
      {
        if ( *(_WORD *)(v16 + 8) )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x34,
            (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\p9await.h",
            v14);
        *(_QWORD *)(v16 + 8) |= 1uLL;
        (*(void (__fastcall **)(_QWORD, __int64))v16)(a1[2], v13);
      }
      goto LABEL_16;
    case 5:
      v11 = a1[2];
      if ( v11 )
      {
        if ( *(_WORD *)(v11 + 8) )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x34,
            (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\p9await.h",
            a4);
        *(_QWORD *)(v11 + 8) |= 1uLL;
        (*(void (**)(void))v11)();
      }
LABEL_16:
      lambda_14a7a5d5c2db807f1a68f78f3c68b6c0_::__lambda_14a7a5d5c2db807f1a68f78f3c68b6c0_(a1 + 340);
      if ( *((_WORD *)a1 + 5) )
        operator delete(a1, 0xAD0u);
      break;
    default:
      __debugbreak();
      break;
  }
}

```

## disassembly

```asm
0x18000f2d0  mov     rax, rsp
0x18000f2d3  mov     [rax+10h], rbx
0x18000f2d7  mov     [rax+18h], rsi
0x18000f2db  mov     [rax+8], rcx
0x18000f2df  push    rdi
0x18000f2e0  push    r14
0x18000f2e2  push    r15
0x18000f2e4  sub     rsp, 0D0h
0x18000f2eb  mov     rdi, rcx
0x18000f2ee  mov     [rsp+0E8h+var_B0], rcx
0x18000f2f3  movzx   eax, word ptr [rdi+8]
0x18000f2f7  mov     [rsp+0E8h+var_B8], ax
0x18000f2fc  mov     r15d, 1
0x18000f302  add     ax, r15w
0x18000f306  cmp     ax, 6; switch 7 cases
0x18000f30a  ja      def_18000F325; jumptable 000000018000F325 default case, cases 1,2
0x18000f310  movsx   rax, ax
0x18000f314  lea     rdx, cs:180000000h
0x18000f31b  mov     ecx, ds:(jpt_18000F325 - 180000000h)[rdx+rax*4]
0x18000f322  add     rcx, rdx
0x18000f325  jmp     rcx; switch jump
0x18000f327  xor     esi, esi; jumptable 000000018000F325 case 4
0x18000f329  jmp     loc_18000F4C8
0x18000f32e  mov     ecx, 0A40h; jumptable 000000018000F325 case 3
0x18000f333  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000f338  lea     r14, [rdi+10h]
0x18000f33c  lea     rcx, [r14+0A90h]
0x18000f343  mov     [rsp+0E8h+var_C8], rax
0x18000f348  add     rax, 20h ; ' '
0x18000f34c  mov     [rdi+18h], rax
0x18000f350  mov     [rsp+0E8h+var_C8], rax
0x18000f355  mov     [rax+0A18h], rcx
0x18000f35c  mov     rax, [rdi+18h]
0x18000f360  mov     [rsp+0E8h+var_C8], rax
0x18000f365  lea     rcx, _lambda_14a7a5d5c2db807f1a68f78f3c68b6c0_$_ResumeCoro$1__operator__
0x18000f36c  mov     [rax], rcx
0x18000f36f  mov     rax, [rdi+18h]
0x18000f373  mov     [rsp+0E8h+var_C8], rax
0x18000f378  mov     dword ptr [rax+8], 10002h
0x18000f37f  mov     rbx, [rdi+18h]
0x18000f383  mov     [rsp+0E8h+var_C8], rbx
0x18000f388  xorps   xmm0, xmm0
0x18000f38b  movups  xmmword ptr [rbx-20h], xmm0
0x18000f38f  movups  xmmword ptr [rbx-10h], xmm0
0x18000f393  mov     rcx, [rdi+18h]
0x18000f397  mov     [rsp+0E8h+var_C8], rcx
0x18000f39c  xor     esi, esi
0x18000f39e  mov     [rcx-20h], rsi
0x18000f3a2  mov     [rcx-18h], sil
0x18000f3a6  add     rcx, 0FFFFFFFFFFFFFFF0h
0x18000f3aa  mov     [rcx], rsi
0x18000f3ad  mov     [rcx+8], rsi
0x18000f3b1  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18000f3b7  nop
0x18000f3b8  mov     [r14], rbx
0x18000f3bb  mov     rax, [rdi+18h]
0x18000f3bf  mov     [rsp+0E8h+var_C8], rax
0x18000f3c4  xor     ecx, ecx
0x18000f3c6  mov     [rax+0A10h], cl
0x18000f3cc  mov     rcx, [rdi+18h]
0x18000f3d0  mov     [rsp+0E8h+var_C8], rcx
0x18000f3d5  call    _lambda_14a7a5d5c2db807f1a68f78f3c68b6c0_$_ResumeCoro$1__operator__
0x18000f3da  nop
0x18000f3db  mov     rax, [r14]
0x18000f3de  mov     [rsp+0E8h+var_C0], rax
0x18000f3e3  mov     dl, [rax-18h]
0x18000f3e6  nop
0x18000f3e7  test    dl, dl
0x18000f3e9  jnz     short loc_18000F44E
0x18000f3eb  lea     eax, [rsi+4]
0x18000f3ee  mov     [rdi+8], ax
0x18000f3f2  mov     rdx, rdi
0x18000f3f5  mov     rcx, r14
0x18000f3f8  call    ?await_suspend@?$Task@X@p9fs@@QEAA_NU?$coroutine_handle@X@experimental@std@@@Z; p9fs::Task<void>::await_suspend(std::experimental::coroutine_handle<void>)
0x18000f3fd  test    al, al
0x18000f3ff  jz      short loc_18000F44E
0x18000f401  jmp     loc_18000F4EA
0x18000f406  mov     rax, [rdi+10h]; jumptable 000000018000F325 case 6
0x18000f40a  mov     [rsp+0E8h+var_C0], rax
0x18000f40f  xor     esi, esi
0x18000f411  test    rax, rax
0x18000f414  jz      short loc_18000F44A
0x18000f416  mov     rcx, [rsp+0E8h]; this
0x18000f41e  cmp     [rax+8], si
0x18000f422  jz      short loc_18000F434
0x18000f424  lea     r8, aOnecoreVmDvSto_1; "onecore\\vm\\dv\\storage\\plan9\\dll\\p"...
0x18000f42b  lea     edx, [rsi+34h]; void *
0x18000f42e  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18000f434  or      [rax+8], r15
0x18000f438  mov     rax, [rax]
0x18000f43b  mov     rcx, [rdi+10h]
0x18000f43f  mov     [rsp+0E8h+var_C0], rcx
0x18000f444  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f449  nop
0x18000f44a  jmp     short loc_18000F4C8
0x18000f44c  xor     esi, esi; jumptable 000000018000F325 case 5
0x18000f44e  mov     rax, [rdi+10h]
0x18000f452  mov     [rsp+0E8h+var_C0], rax
0x18000f457  lea     rbx, [rax-10h]
0x18000f45b  mov     rcx, rbx
0x18000f45e  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x18000f464  test    al, al
0x18000f466  jz      short loc_18000F480
0x18000f468  lea     rcx, [rdi+0A80h]; this
0x18000f46f  mov     rdx, rbx; struct std::exception_ptr *
0x18000f472  call    ??0exception_ptr@std@@QEAA@AEBV01@@Z; std::exception_ptr::exception_ptr(std::exception_ptr const &)
0x18000f477  mov     rcx, rax
0x18000f47a  call    ?rethrow_exception@std@@YAXVexception_ptr@1@@Z; std::rethrow_exception(std::exception_ptr)
0x18000f480  mov     rax, [rdi+10h]
0x18000f484  mov     [rsp+0E8h+var_C0], rax
0x18000f489  test    rax, rax
0x18000f48c  jz      short loc_18000F4C4
0x18000f48e  mov     rcx, [rsp+0E8h]; this
0x18000f496  cmp     [rax+8], si
0x18000f49a  jz      short loc_18000F4AE
0x18000f49c  lea     r8, aOnecoreVmDvSto_1; "onecore\\vm\\dv\\storage\\plan9\\dll\\p"...
0x18000f4a3  mov     edx, 34h ; '4'; void *
0x18000f4a8  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18000f4ae  or      [rax+8], r15
0x18000f4b2  mov     rax, [rax]
0x18000f4b5  mov     rcx, [rdi+10h]
0x18000f4b9  mov     [rsp+0E8h+var_C0], rcx
0x18000f4be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f4c3  nop
0x18000f4c4  jmp     short loc_18000F4C8
0x18000f4c6  xor     esi, esi; jumptable 000000018000F325 case 0
0x18000f4c8  lea     rcx, [rdi+0AA0h]
0x18000f4cf  call    _lambda_14a7a5d5c2db807f1a68f78f3c68b6c0_____lambda_14a7a5d5c2db807f1a68f78f3c68b6c0_
0x18000f4d4  cmp     [rdi+0Ah], si
0x18000f4d8  jz      short loc_18000F4EA
0x18000f4da  mov     edx, 0AD0h; unsigned __int64
0x18000f4df  mov     rcx, rdi; void *
0x18000f4e2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000f4e7  jmp     short loc_18000F4EA
0x18000f4e9  int     3; Trap to Debugger
0x18000f4ea  lea     r11, [rsp+0E8h+var_18]
0x18000f4f2  mov     rbx, [r11+28h]
0x18000f4f6  mov     rsi, [r11+30h]
0x18000f4fa  mov     rsp, r11
0x18000f4fd  pop     r15
0x18000f4ff  pop     r14
0x18000f501  pop     rdi
0x18000f502  retn
```
