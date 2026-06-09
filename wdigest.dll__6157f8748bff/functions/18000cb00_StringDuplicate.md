# StringDuplicate

- ea: `0x18000cb00`
- end: `0x18000cc94`
- name: `StringDuplicate`
- size: `404`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `10`
- callee_count: `6`
- tags: ``

## callers

- `0x180003a50`
- `0x180004cb0`
- `0x18001c8e0`
- `0x18001e4b0`
- `0x1800206d0`
- `0x180022ffc`
- `0x1800283d8`
- `0x180028ff0`
- `0x18002ea3c`
- `0x18002fb80`

## callees

- `0x18000cb00`
- `0x180011fec`
- `0x180013304`
- `0x180032ec8`
- `0x1800377bc`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000cc0c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000cc0c`

## pseudocode

```c
__int64 __fastcall StringDuplicate(__int64 a1, const void **a2)
{
  __int64 result; // rax
  int v5; // eax
  unsigned int v6; // r14d
  void *v7; // rax
  void *v8; // rbp
  HLOCAL v9; // rax

  result = 0;
  *(_QWORD *)(a1 + 8) = 0;
  *(_DWORD *)a1 = 0;
  if ( a2 && a2[1] )
  {
    v5 = *(unsigned __int16 *)a2;
    if ( (_WORD)v5 == 0xFFFF )
    {
      return 3221225485LL;
    }
    else
    {
      v6 = v5 + 1;
      if ( g_NtDigestState == 1 )
      {
        v7 = (void *)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)&g_LsaFunctions + 40LL))(v6);
        v8 = v7;
        if ( v7 )
          memset_0(v7, 0, v6);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
          WPP_SF_Lq(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_5a1eec0057703498b5d13460810c8614_Traceguids, v6, v8);
      }
      else
      {
        v9 = LocalAlloc(0x40u, v6);
        v8 = v9;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
          WPP_SF_Lq(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_5a1eec0057703498b5d13460810c8614_Traceguids, v6, v9);
      }
      *(_QWORD *)(a1 + 8) = v8;
      if ( v8 )
      {
        *(_WORD *)a1 = *(_WORD *)a2;
        *(_WORD *)(a1 + 2) = *(_WORD *)a2 + 1;
        memcpy_0(v8, a2[1], *(unsigned __int16 *)a2);
        result = 0;
        *(_BYTE *)(*(unsigned __int16 *)a2 + *(_QWORD *)(a1 + 8)) = 0;
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            0xEu,
            (const GUID *)WPP_5a1eec0057703498b5d13460810c8614_Traceguids);
        return 2148074240LL;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000cb00  push    rbx
0x18000cb02  push    rsi
0x18000cb03  push    rdi
0x18000cb04  sub     rsp, 30h
0x18000cb08  xor     esi, esi
0x18000cb0a  xor     eax, eax
0x18000cb0c  mov     [rcx+8], rsi
0x18000cb10  mov     rdi, rdx
0x18000cb13  mov     [rcx], eax
0x18000cb15  mov     rbx, rcx
0x18000cb18  test    rdx, rdx
0x18000cb1b  jz      loc_18000CBE9
0x18000cb21  cmp     [rdx+8], rax
0x18000cb25  jz      loc_18000CBE9
0x18000cb2b  movzx   eax, word ptr [rdx]
0x18000cb2e  mov     ecx, 0FFFEh
0x18000cb33  cmp     ax, cx
0x18000cb36  ja      loc_18000CC5B
0x18000cb3c  cmp     cs:g_NtDigestState, 1
0x18000cb43  mov     [rsp+48h+arg_0], rbp
0x18000cb48  mov     [rsp+48h+arg_8], r14
0x18000cb4d  lea     r14d, [rax+1]
0x18000cb51  mov     [rsp+48h+arg_10], r15
0x18000cb56  jnz     loc_18000CC04
0x18000cb5c  mov     rax, cs:g_LsaFunctions
0x18000cb63  mov     ecx, r14d
0x18000cb66  mov     rax, [rax+28h]
0x18000cb6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb6f  mov     rbp, rax
0x18000cb72  test    rax, rax
0x18000cb75  jz      short loc_18000CB84
0x18000cb77  mov     r8d, r14d; Size
0x18000cb7a  xor     edx, edx; Val
0x18000cb7c  mov     rcx, rax; void *
0x18000cb7f  call    memset_0
0x18000cb84  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cb8b  lea     r15, WPP_GLOBAL_Control
0x18000cb92  cmp     rcx, r15
0x18000cb95  jz      short loc_18000CBA4
0x18000cb97  test    dword ptr [rcx+1Ch], 100h
0x18000cb9e  jnz     loc_18000CC68
0x18000cba4  mov     r14, [rsp+48h+arg_8]
0x18000cba9  mov     [rbx+8], rbp
0x18000cbad  test    rbp, rbp
0x18000cbb0  jz      short loc_18000CBF1
0x18000cbb2  movzx   ecx, word ptr [rdi]
0x18000cbb5  mov     [rbx], cx
0x18000cbb8  movzx   ecx, word ptr [rdi]
0x18000cbbb  inc     cx
0x18000cbbe  mov     [rbx+2], cx
0x18000cbc2  mov     rcx, rbp; void *
0x18000cbc5  movzx   r8d, word ptr [rdi]; Size
0x18000cbc9  mov     rdx, [rdi+8]; Src
0x18000cbcd  call    memcpy_0
0x18000cbd2  movzx   edx, word ptr [rdi]
0x18000cbd5  mov     eax, esi
0x18000cbd7  mov     rcx, [rbx+8]
0x18000cbdb  mov     [rdx+rcx], sil
0x18000cbdf  mov     rbp, [rsp+48h+arg_0]
0x18000cbe4  mov     r15, [rsp+48h+arg_10]
0x18000cbe9  add     rsp, 30h
0x18000cbed  pop     rdi
0x18000cbee  pop     rsi
0x18000cbef  pop     rbx
0x18000cbf0  retn
0x18000cbf1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cbf8  cmp     rcx, r15
0x18000cbfb  jnz     short loc_18000CC74
0x18000cbfd  mov     eax, 80090300h
0x18000cc02  jmp     short loc_18000CBDF
0x18000cc04  mov     edx, r14d; uBytes
0x18000cc07  mov     ecx, 40h ; '@'; uFlags
0x18000cc0c  call    cs:__imp_LocalAlloc
0x18000cc12  mov     rbp, rax
0x18000cc15  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cc1c  lea     r15, WPP_GLOBAL_Control
0x18000cc23  cmp     rcx, r15
0x18000cc26  jz      loc_18000CBA4
0x18000cc2c  test    dword ptr [rcx+1Ch], 100h
0x18000cc33  jz      loc_18000CBA4
0x18000cc39  mov     edx, 1Dh
0x18000cc3e  mov     [rsp+48h+var_28], rax
0x18000cc43  mov     rcx, [rcx+10h]
0x18000cc47  lea     r8, WPP_5a1eec0057703498b5d13460810c8614_Traceguids
0x18000cc4e  mov     r9d, r14d
0x18000cc51  call    WPP_SF_Lq
0x18000cc56  jmp     loc_18000CBA4
0x18000cc5b  mov     eax, 0C000000Dh
0x18000cc60  add     rsp, 30h
0x18000cc64  pop     rdi
0x18000cc65  pop     rsi
0x18000cc66  pop     rbx
0x18000cc67  retn
0x18000cc68  mov     edx, 1Ch
0x18000cc6d  mov     [rsp+48h+var_28], rbp
0x18000cc72  jmp     short loc_18000CC43
0x18000cc74  test    byte ptr [rcx+1Ch], 1
0x18000cc78  jz      short loc_18000CBFD
0x18000cc7a  mov     rcx, [rcx+10h]
0x18000cc7e  lea     r8, WPP_5a1eec0057703498b5d13460810c8614_Traceguids
0x18000cc85  mov     edx, 0Eh
0x18000cc8a  call    WPP_SF_
0x18000cc8f  jmp     loc_18000CBFD
```
