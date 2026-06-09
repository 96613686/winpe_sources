# UnicodeStringDuplicate

- ea: `0x180003520`
- end: `0x1800036c0`
- name: `UnicodeStringDuplicate`
- size: `416`
- prototype: ``
- caller_count: `10`
- callee_count: `6`
- tags: ``

## callers

- `0x180001bb0`
- `0x18001a6c0`
- `0x18001b2f8`
- `0x180021f88`
- `0x180022ffc`
- `0x18002357c`
- `0x180025a14`
- `0x180026ad0`
- `0x1800283d8`
- `0x18002b2b8`

## callees

- `0x180003520`
- `0x180011fec`
- `0x180013304`
- `0x180032ec8`
- `0x1800377bc`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003634`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003634`

## pseudocode

```c
__int64 __fastcall UnicodeStringDuplicate(__int64 a1, const void **a2)
{
  __int64 result; // rax
  int v5; // eax
  unsigned int v6; // ebp
  void *v7; // rax
  void *v8; // rsi
  HLOCAL v9; // rax

  result = 0;
  *(_QWORD *)(a1 + 8) = 0;
  *(_DWORD *)a1 = 0;
  if ( a2 && a2[1] )
  {
    v5 = *(unsigned __int16 *)a2;
    if ( (unsigned __int16)v5 > 0xFFFDu )
    {
      return 3221225485LL;
    }
    else
    {
      v6 = v5 + 2;
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
        *(_WORD *)(a1 + 2) = *(_WORD *)a2 + 2;
        memcpy_0(v8, a2[1], *(unsigned __int16 *)a2);
        result = 0;
        *(_WORD *)(*(_QWORD *)(a1 + 8) + 2 * ((unsigned __int64)*(unsigned __int16 *)a2 >> 1)) = 0;
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            0xAu,
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
0x180003520  push    rbx
0x180003522  push    rdi
0x180003523  push    r15
0x180003525  sub     rsp, 30h
0x180003529  xor     r15d, r15d
0x18000352c  xor     eax, eax
0x18000352e  mov     [rcx+8], r15
0x180003532  mov     rbx, rdx
0x180003535  mov     [rcx], eax
0x180003537  mov     rdi, rcx
0x18000353a  test    rdx, rdx
0x18000353d  jz      loc_180003616
0x180003543  cmp     [rdx+8], rax
0x180003547  jz      loc_180003616
0x18000354d  movzx   eax, word ptr [rdx]
0x180003550  mov     ecx, 0FFFDh
0x180003555  cmp     ax, cx
0x180003558  ja      loc_18000361F
0x18000355e  cmp     cs:g_NtDigestState, 1
0x180003565  mov     [rsp+48h+arg_0], rbp
0x18000356a  lea     ebp, [rax+2]
0x18000356d  mov     [rsp+48h+arg_8], rsi
0x180003572  mov     [rsp+48h+arg_10], r14
0x180003577  jnz     loc_18000362D
0x18000357d  mov     rax, cs:g_LsaFunctions
0x180003584  mov     ecx, ebp
0x180003586  mov     rax, [rax+28h]
0x18000358a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000358f  mov     rsi, rax
0x180003592  test    rax, rax
0x180003595  jz      short loc_1800035A4
0x180003597  mov     r8d, ebp; Size
0x18000359a  xor     edx, edx; Val
0x18000359c  mov     rcx, rax; void *
0x18000359f  call    memset_0
0x1800035a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800035ab  lea     r14, WPP_GLOBAL_Control
0x1800035b2  cmp     rcx, r14
0x1800035b5  jz      short loc_1800035C4
0x1800035b7  test    dword ptr [rcx+1Ch], 100h
0x1800035be  jnz     loc_180003683
0x1800035c4  mov     rbp, [rsp+48h+arg_0]
0x1800035c9  mov     [rdi+8], rsi
0x1800035cd  test    rsi, rsi
0x1800035d0  jz      loc_18000368F
0x1800035d6  movzx   ecx, word ptr [rbx]
0x1800035d9  mov     [rdi], cx
0x1800035dc  movzx   ecx, word ptr [rbx]
0x1800035df  add     cx, 2
0x1800035e3  mov     [rdi+2], cx
0x1800035e7  mov     rcx, rsi; void *
0x1800035ea  movzx   r8d, word ptr [rbx]; Size
0x1800035ee  mov     rdx, [rbx+8]; Src
0x1800035f2  call    memcpy_0
0x1800035f7  movzx   r8d, word ptr [rbx]
0x1800035fb  mov     eax, r15d
0x1800035fe  mov     rdx, [rdi+8]
0x180003602  shr     r8, 1
0x180003605  xor     ecx, ecx
0x180003607  mov     [rdx+r8*2], cx
0x18000360c  mov     rsi, [rsp+48h+arg_8]
0x180003611  mov     r14, [rsp+48h+arg_10]
0x180003616  add     rsp, 30h
0x18000361a  pop     r15
0x18000361c  pop     rdi
0x18000361d  pop     rbx
0x18000361e  retn
0x18000361f  mov     eax, 0C000000Dh
0x180003624  add     rsp, 30h
0x180003628  pop     r15
0x18000362a  pop     rdi
0x18000362b  pop     rbx
0x18000362c  retn
0x18000362d  mov     edx, ebp; uBytes
0x18000362f  mov     ecx, 40h ; '@'; uFlags
0x180003634  call    cs:__imp_LocalAlloc
0x18000363a  mov     rsi, rax
0x18000363d  mov     rcx, cs:WPP_GLOBAL_Control
0x180003644  lea     r14, WPP_GLOBAL_Control
0x18000364b  cmp     rcx, r14
0x18000364e  jz      loc_1800035C4
0x180003654  test    dword ptr [rcx+1Ch], 100h
0x18000365b  jz      loc_1800035C4
0x180003661  mov     edx, 1Dh
0x180003666  mov     [rsp+48h+var_28], rax
0x18000366b  mov     rcx, [rcx+10h]
0x18000366f  lea     r8, WPP_5a1eec0057703498b5d13460810c8614_Traceguids
0x180003676  mov     r9d, ebp
0x180003679  call    WPP_SF_Lq
0x18000367e  jmp     loc_1800035C4
0x180003683  mov     edx, 1Ch
0x180003688  mov     [rsp+48h+var_28], rsi
0x18000368d  jmp     short loc_18000366B
0x18000368f  mov     rcx, cs:WPP_GLOBAL_Control
0x180003696  cmp     rcx, r14
0x180003699  jz      short loc_1800036B6
0x18000369b  test    byte ptr [rcx+1Ch], 1
0x18000369f  jz      short loc_1800036B6
0x1800036a1  mov     rcx, [rcx+10h]
0x1800036a5  lea     r8, WPP_5a1eec0057703498b5d13460810c8614_Traceguids
0x1800036ac  mov     edx, 0Ah
0x1800036b1  call    WPP_SF_
0x1800036b6  mov     eax, 80090300h
0x1800036bb  jmp     loc_18000360C
```
