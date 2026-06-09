# AddMfeToForwarder

- ea: `0x18001f11c`
- end: `0x18001f32c`
- name: `AddMfeToForwarder`
- size: `528`
- prototype: ``
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x180017f48`
- `0x180018070`
- `0x180019de0`
- `0x18001c790`
- `0x18001d908`

## callees

- `0x18001f11c`
- `0x18001f7e8`
- `0x18001f952`
- `0x18001f980`
- `0x180020010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x18001f190`
- `KERNEL32!HeapAlloc` at `0x18001f190`
- `KERNEL32!HeapFree` at `0x18001f2a2`
- `KERNEL32!HeapFree` at `0x18001f2a2`
- `rtutils!RouterLogEventA` at `0x18001f2fe`
- `rtutils!RouterLogEventA` at `0x18001f2fe`

## string_xrefs

- `0x18001f2bd`: `AddMfeToForwarder : Arithmatic Overflow error. Failed to create MFE `
- `0x18001f1ab`: `AddMfeToForwarder : Failed to create MFE of size : %x`

## pseudocode

```c
void __fastcall AddMfeToForwarder(__int64 a1, unsigned int *a2, int a3)
{
  unsigned __int64 v6; // rax
  _DWORD *v7; // rax
  _DWORD *v8; // rbx
  __int64 v9; // r8
  __int64 v10; // rsi
  unsigned int v11; // eax
  int v12; // eax
  __int64 **v13; // rdi
  __int64 *i; // r8
  __int64 v15; // rcx
  __int64 v16; // rdx
  int v17; // [rsp+30h] [rbp-828h] BYREF
  _BYTE v18[2044]; // [rsp+34h] [rbp-824h] BYREF

  v17 = 0;
  memset_0(v18, 0, sizeof(v18));
  v6 = 16LL * a2[20];
  if ( v6 > 0xFFFFFFFF || (int)v6 + 32 < (unsigned int)v6 )
  {
    if ( qword_18002B8A8 )
      ((void (__fastcall *)(__int64, __int64, const wchar_t *))gMgmTemplateFunc)(
        gMgmEtwContext,
        qword_18002B8A8,
        L"AddMfeToForwarder : Arithmatic Overflow error. Failed to create MFE ");
    if ( dword_18002BA54 )
      RouterLogEventA(qword_18002BA58, 1u, 0xC353u, 0, 0, 0x216u);
  }
  else
  {
    v7 = HeapAlloc(hHeap, 0, (unsigned int)(v6 + 32));
    v8 = v7;
    if ( v7 )
    {
      v10 = 0;
      memset_0(v7, 0, 16 * (a2[20] + 2LL));
      *v8 = *(_DWORD *)(a1 + 32);
      v8[1] = a2[26];
      v8[2] = a2[27];
      if ( a2[20] )
        v11 = a2[28];
      else
        v11 = 0;
      v8[3] = v11;
      v8[4] = a2[20];
      v12 = 0;
      if ( !a2[20] )
        v12 = a3;
      v13 = (__int64 **)(a2 + 22);
      v8[5] = v12;
      for ( i = *v13; i != (__int64 *)v13; i = (__int64 *)*i )
      {
        v15 = 2 * (v10 + 2);
        v16 = 2LL * (unsigned int)v10;
        v10 = (unsigned int)(v10 + 1);
        v8[2 * v15] = *((_DWORD *)i + 4);
        *(_QWORD *)&v8[2 * v16 + 9] = *((unsigned int *)i + 5);
      }
      if ( qword_18002B938 )
        qword_18002B938(v8);
      HeapFree(hHeap, 0, v8);
    }
    else
    {
      if ( qword_18002B8A8 )
      {
        v9 = a2[20] + 2LL;
        LOWORD(v17) = 0;
        FormatRRASErrorString(&v17, L"AddMfeToForwarder : Failed to create MFE of size : %x", 16 * v9);
        ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v17);
      }
      if ( dword_18002BA54 )
        RouterLogEventA(qword_18002BA58, 1u, 0xC353u, 0, 0, 8u);
    }
  }
}

```

## disassembly

```asm
0x18001f11c  mov     [rsp+arg_0], rbx
0x18001f121  mov     [rsp+arg_10], rbp
0x18001f126  push    rsi
0x18001f127  push    rdi
0x18001f128  push    r14
0x18001f12a  sub     rsp, 840h
0x18001f131  mov     rax, cs:__security_cookie
0x18001f138  xor     rax, rsp
0x18001f13b  mov     [rsp+858h+var_28], rax
0x18001f143  mov     r14d, r8d
0x18001f146  mov     rdi, rdx
0x18001f149  mov     rbp, rcx
0x18001f14c  xor     eax, eax
0x18001f14e  xor     edx, edx; Val
0x18001f150  mov     [rsp+858h+var_828], eax
0x18001f154  mov     r8d, 7FCh; Size
0x18001f15a  lea     rcx, [rsp+858h+var_824]; void *
0x18001f15f  call    memset_0
0x18001f164  mov     eax, [rdi+50h]
0x18001f167  mov     ecx, 0FFFFFFFFh
0x18001f16c  shl     rax, 4
0x18001f170  cmp     rax, rcx
0x18001f173  ja      loc_18001F2AA
0x18001f179  lea     ecx, [rax+20h]
0x18001f17c  cmp     ecx, eax
0x18001f17e  jb      loc_18001F2AA
0x18001f184  mov     r8d, ecx; dwBytes
0x18001f187  xor     edx, edx; dwFlags
0x18001f189  mov     rcx, cs:hHeap; hHeap
0x18001f190  call    cs:__imp_HeapAlloc
0x18001f196  mov     rbx, rax
0x18001f199  test    rax, rax
0x18001f19c  jnz     short loc_18001F202
0x18001f19e  cmp     cs:qword_18002B8A8, rax
0x18001f1a5  jz      short loc_18001F1E8
0x18001f1a7  mov     r8d, [rdi+50h]
0x18001f1ab  lea     rdx, aAddmfetoforwar; "AddMfeToForwarder : Failed to create MF"...
0x18001f1b2  add     r8, 2
0x18001f1b6  mov     word ptr [rsp+858h+var_828], ax
0x18001f1bb  shl     r8, 4
0x18001f1bf  lea     rcx, [rsp+858h+var_828]
0x18001f1c4  call    FormatRRASErrorString
0x18001f1c9  mov     rdx, cs:qword_18002B8A8
0x18001f1d0  lea     r8, [rsp+858h+var_828]
0x18001f1d5  mov     rcx, cs:gMgmEtwContext
0x18001f1dc  mov     rax, cs:gMgmTemplateFunc
0x18001f1e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f1e8  cmp     cs:dword_18002BA54, 1
0x18001f1ef  jb      loc_18001F304
0x18001f1f5  mov     [rsp+858h+dwErrorCode], 8
0x18001f1fd  jmp     loc_18001F2E1
0x18001f202  mov     r8d, [rdi+50h]
0x18001f206  xor     edx, edx; Val
0x18001f208  add     r8, 2
0x18001f20c  mov     rcx, rbx; void *
0x18001f20f  shl     r8, 4; Size
0x18001f213  xor     esi, esi
0x18001f215  call    memset_0
0x18001f21a  mov     eax, [rbp+20h]
0x18001f21d  mov     [rbx], eax
0x18001f21f  mov     eax, [rdi+68h]
0x18001f222  mov     [rbx+4], eax
0x18001f225  mov     eax, [rdi+6Ch]
0x18001f228  mov     [rbx+8], eax
0x18001f22b  cmp     [rdi+50h], esi
0x18001f22e  jz      short loc_18001F235
0x18001f230  mov     eax, [rdi+70h]
0x18001f233  jmp     short loc_18001F237
0x18001f235  xor     eax, eax
0x18001f237  mov     [rbx+0Ch], eax
0x18001f23a  mov     eax, [rdi+50h]
0x18001f23d  mov     [rbx+10h], eax
0x18001f240  xor     eax, eax
0x18001f242  cmp     [rdi+50h], eax
0x18001f245  cmovz   eax, r14d
0x18001f249  add     rdi, 58h ; 'X'
0x18001f24d  mov     [rbx+14h], eax
0x18001f250  mov     r8, [rdi]
0x18001f253  jmp     short loc_18001F27D
0x18001f255  mov     eax, [r8+10h]
0x18001f259  lea     rcx, [rsi+2]
0x18001f25d  add     rcx, rcx
0x18001f260  mov     edx, esi
0x18001f262  add     rdx, rdx
0x18001f265  inc     esi
0x18001f267  mov     [rbx+rcx*8], eax
0x18001f26a  mov     eax, [r8+14h]
0x18001f26e  mov     [rbx+rdx*8+24h], eax
0x18001f272  mov     dword ptr [rbx+rdx*8+28h], 0
0x18001f27a  mov     r8, [r8]
0x18001f27d  cmp     r8, rdi
0x18001f280  jnz     short loc_18001F255
0x18001f282  mov     rax, cs:qword_18002B938
0x18001f289  test    rax, rax
0x18001f28c  jz      short loc_18001F296
0x18001f28e  mov     rcx, rbx
0x18001f291  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f296  mov     rcx, cs:hHeap; hHeap
0x18001f29d  mov     r8, rbx; lpMem
0x18001f2a0  xor     edx, edx; dwFlags
0x18001f2a2  call    cs:__imp_HeapFree
0x18001f2a8  jmp     short loc_18001F304
0x18001f2aa  mov     rdx, cs:qword_18002B8A8
0x18001f2b1  test    rdx, rdx
0x18001f2b4  jz      short loc_18001F2D0
0x18001f2b6  mov     rcx, cs:gMgmEtwContext
0x18001f2bd  lea     r8, aAddmfetoforwar_0; "AddMfeToForwarder : Arithmatic Overflow"...
0x18001f2c4  mov     rax, cs:gMgmTemplateFunc
0x18001f2cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f2d0  cmp     cs:dword_18002BA54, 1
0x18001f2d7  jb      short loc_18001F304
0x18001f2d9  mov     [rsp+858h+dwErrorCode], 216h; dwErrorCode
0x18001f2e1  mov     rcx, cs:qword_18002BA58; hLogHandle
0x18001f2e8  xor     r9d, r9d; dwSubStringCount
0x18001f2eb  mov     r8d, 0C353h; dwMessageId
0x18001f2f1  mov     [rsp+858h+plpszSubStringArray], 0; plpszSubStringArray
0x18001f2fa  lea     edx, [r9+1]; dwEventType
0x18001f2fe  call    cs:__imp_RouterLogEventA
0x18001f304  mov     rcx, [rsp+858h+var_28]
0x18001f30c  xor     rcx, rsp; StackCookie
0x18001f30f  call    __security_check_cookie
0x18001f314  lea     r11, [rsp+858h+var_18]
0x18001f31c  mov     rbx, [r11+20h]
0x18001f320  mov     rbp, [r11+30h]
0x18001f324  mov     rsp, r11
0x18001f327  pop     r14
0x18001f329  pop     rdi
0x18001f32a  pop     rsi
0x18001f32b  retn
```
