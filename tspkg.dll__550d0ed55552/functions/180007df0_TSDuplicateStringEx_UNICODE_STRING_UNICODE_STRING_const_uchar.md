# TSDuplicateStringEx(_UNICODE_STRING *,_UNICODE_STRING const *,uchar)

- ea: `0x180007df0`
- end: `0x180007eec`
- name: `?TSDuplicateStringEx@@YAJPEAU_UNICODE_STRING@@PEBU1@E@Z`
- size: `252`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *, const struct _UNICODE_STRING *, unsigned __int8)`
- caller_count: `16`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180006650`
- `0x180009b2c`
- `0x180009f18`
- `0x180013ec8`
- `0x180013f70`
- `0x18001449c`
- `0x180014a84`
- `0x180014e90`
- `0x180015304`
- `0x180017314`
- `0x180019cc4`
- `0x18001a0e0`
- `0x18001a12c`
- `0x18001b000`
- `0x18001b1f0`
- `0x18001b810`

## callees

- `0x180007df0`
- `0x18000c1a4`
- `0x18001c63c`
- `0x18001d010`

## pseudocode

```c
__int64 __fastcall TSDuplicateStringEx(struct _UNICODE_STRING *a1, const struct _UNICODE_STRING *a2)
{
  int Length; // eax
  __int64 result; // rax
  size_t v6; // rbp
  WCHAR *v7; // rsi
  WCHAR *v8; // rax

  if ( !a2 || !a2->Buffer )
  {
    a1->Buffer = 0;
    result = 0;
    *(_DWORD *)&a1->Length = 0;
    return result;
  }
  Length = a2->Length;
  if ( (unsigned __int16)Length > 0xFFFCu )
  {
    result = 3221225734LL;
    a1->Buffer = 0;
    return result;
  }
  v6 = (unsigned int)(Length + 2);
  if ( TSGlobalState == 1 )
  {
    v7 = (WCHAR *)((__int64 (__fastcall *)(_QWORD))TSGlobalLsaFunctions->AllocatePrivateHeap)((unsigned int)v6);
  }
  else
  {
    v8 = (WCHAR *)((__int64 (__fastcall *)(_QWORD))TSGlobalDllFunctions->AllocateHeap)((unsigned int)v6);
    v7 = v8;
    if ( v8 )
    {
      memset_0(v8, 0, v6);
      a1->Buffer = v7;
      goto LABEL_12;
    }
  }
  a1->Buffer = v7;
  if ( v7 )
  {
LABEL_12:
    a1->Length = a2->Length;
    a1->MaximumLength = v6;
    memcpy_0(v7, a2->Buffer, a2->Length);
    a1->Buffer[(unsigned __int64)a2->Length >> 1] = 0;
    return 0;
  }
  return 3221225626LL;
}

```

## disassembly

```asm
0x180007df0  mov     [rsp+arg_10], rbx
0x180007df5  push    rdi
0x180007df6  sub     rsp, 20h
0x180007dfa  mov     rbx, rdx
0x180007dfd  mov     rdi, rcx
0x180007e00  test    rdx, rdx
0x180007e03  jz      loc_180007ED7
0x180007e09  cmp     qword ptr [rdx+8], 0
0x180007e0e  jz      loc_180007ED7
0x180007e14  movzx   eax, word ptr [rdx]
0x180007e17  mov     ecx, 0FFFCh
0x180007e1c  cmp     ax, cx
0x180007e1f  jbe     short loc_180007E2E
0x180007e21  xor     edx, edx
0x180007e23  mov     eax, 0C0000106h
0x180007e28  mov     [rdi+8], rdx
0x180007e2c  jmp     short loc_180007E74
0x180007e2e  cmp     cs:?TSGlobalState@@3W4_TS_STATE@@A, 1; _TS_STATE TSGlobalState
0x180007e35  mov     [rsp+28h+arg_0], rbp
0x180007e3a  lea     ebp, [rax+2]
0x180007e3d  mov     [rsp+28h+arg_8], rsi
0x180007e42  jnz     short loc_180007E7F
0x180007e44  mov     rax, cs:?TSGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * TSGlobalLsaFunctions
0x180007e4b  mov     ecx, ebp
0x180007e4d  mov     rax, [rax+180h]
0x180007e54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e59  mov     rsi, rax
0x180007e5c  mov     [rdi+8], rsi
0x180007e60  test    rsi, rsi
0x180007e63  jnz     short loc_180007EA9
0x180007e65  mov     eax, 0C000009Ah
0x180007e6a  mov     rbp, [rsp+28h+arg_0]
0x180007e6f  mov     rsi, [rsp+28h+arg_8]
0x180007e74  mov     rbx, [rsp+28h+arg_10]
0x180007e79  add     rsp, 20h
0x180007e7d  pop     rdi
0x180007e7e  retn
0x180007e7f  mov     rax, cs:?TSGlobalDllFunctions@@3PEAU_SECPKG_DLL_FUNCTIONS@@EA; _SECPKG_DLL_FUNCTIONS * TSGlobalDllFunctions
0x180007e86  mov     ecx, ebp
0x180007e88  mov     rax, [rax]
0x180007e8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e90  mov     rsi, rax
0x180007e93  test    rax, rax
0x180007e96  jz      short loc_180007E5C
0x180007e98  mov     r8, rbp; Size
0x180007e9b  xor     edx, edx; Val
0x180007e9d  mov     rcx, rax; void *
0x180007ea0  call    memset_0
0x180007ea5  mov     [rdi+8], rsi
0x180007ea9  movzx   eax, word ptr [rbx]
0x180007eac  mov     rcx, rsi; void *
0x180007eaf  mov     [rdi], ax
0x180007eb2  mov     [rdi+2], bp
0x180007eb6  movzx   r8d, word ptr [rbx]; Size
0x180007eba  mov     rdx, [rbx+8]; Src
0x180007ebe  call    memcpy_0
0x180007ec3  movzx   ecx, word ptr [rbx]
0x180007ec6  xor     edx, edx
0x180007ec8  mov     rax, [rdi+8]
0x180007ecc  shr     rcx, 1
0x180007ecf  mov     [rax+rcx*2], dx
0x180007ed3  xor     eax, eax
0x180007ed5  jmp     short loc_180007E6A
0x180007ed7  mov     rbx, [rsp+28h+arg_10]
0x180007edc  xor     edx, edx
0x180007ede  mov     [rcx+8], rdx
0x180007ee2  xor     eax, eax
0x180007ee4  mov     [rcx], edx
0x180007ee6  add     rsp, 20h
0x180007eea  pop     rdi
0x180007eeb  retn
```
