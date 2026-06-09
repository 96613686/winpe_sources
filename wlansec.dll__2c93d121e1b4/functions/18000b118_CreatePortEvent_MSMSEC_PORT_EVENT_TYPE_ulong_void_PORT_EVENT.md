# CreatePortEvent(MSMSEC_PORT_EVENT_TYPE,ulong,void *,PORT_EVENT * *)

- ea: `0x18000b118`
- end: `0x18000b2b3`
- name: `?CreatePortEvent@@YAKW4MSMSEC_PORT_EVENT_TYPE@@KPEAXPEAPEAUPORT_EVENT@@@Z`
- size: `411`
- prototype: ``
- caller_count: `17`
- callee_count: `5`
- tags: ``

## callers

- `0x180009f3c`
- `0x1800193cc`
- `0x180027c70`
- `0x1800334c0`
- `0x1800345f4`
- `0x180036a5c`
- `0x180039210`
- `0x18003bd0c`
- `0x18003d95c`
- `0x18004145c`
- `0x180062dc4`
- `0x180064350`
- `0x180064780`
- `0x180064edc`
- `0x180065c18`
- `0x180066244`
- `0x180066d68`

## callees

- `0x1800063b0`
- `0x18000892c`
- `0x180008998`
- `0x18000b118`
- `0x18000b2c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b16e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b16e`

## pseudocode

```c
__int64 __fastcall CreatePortEvent(int a1, int a2, __int64 a3, __int64 a4)
{
  unsigned int v8; // eax
  DWORD v9; // ebx
  __int64 v10; // rbp
  DWORD LastError; // eax
  PVOID *v12; // rcx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 10, &WPP_4b473b0d41083bd40dfc61d99b047aaf_Traceguids);
  if ( a2 )
    v8 = 16 * a2 + 40;
  else
    v8 = 56;
  v9 = 0;
  v10 = AllocWLMem(v8);
  if ( !v10 )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_13d7b2876eef3b3479d595a943243812_Traceguids, LastError);
    }
  }
  *(_QWORD *)a4 = v10;
  v12 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_13d7b2876eef3b3479d595a943243812_Traceguids, v10);
    v12 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !v9 )
  {
    *(_DWORD *)(*(_QWORD *)a4 + 16LL) = a1;
    *(_DWORD *)(*(_QWORD *)a4 + 32LL) = a2;
    *(_QWORD *)(*(_QWORD *)a4 + 24LL) = a3;
LABEL_13:
    v12 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_14;
  }
  if ( v12 == &WPP_GLOBAL_Control )
    return v9;
  if ( (*((_BYTE *)v12 + 68) & 1) != 0 )
  {
    WPP_SF_d(v12[7], 11, &WPP_4b473b0d41083bd40dfc61d99b047aaf_Traceguids, v9);
    goto LABEL_13;
  }
LABEL_14:
  if ( v12 != &WPP_GLOBAL_Control && (*((_DWORD *)v12 + 17) & 0x100) != 0 )
    WPP_SF_d(v12[7], 12, &WPP_4b473b0d41083bd40dfc61d99b047aaf_Traceguids, v9);
  return v9;
}

```

## disassembly

```asm
0x18000b118  push    rbx
0x18000b11a  push    rbp
0x18000b11b  push    rsi
0x18000b11c  push    rdi
0x18000b11d  push    r12
0x18000b11f  push    r14
0x18000b121  push    r15
0x18000b123  sub     rsp, 20h
0x18000b127  mov     rdi, r9
0x18000b12a  mov     r14, r8
0x18000b12d  mov     esi, edx
0x18000b12f  mov     r15d, ecx
0x18000b132  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b139  lea     r12, WPP_GLOBAL_Control
0x18000b140  cmp     rcx, r12
0x18000b143  jz      short loc_18000B152
0x18000b145  test    dword ptr [rcx+44h], 100h
0x18000b14c  jnz     loc_18000B1F1
0x18000b152  test    esi, esi
0x18000b154  jnz     loc_18000B1E4
0x18000b15a  lea     eax, [rsi+38h]
0x18000b15d  mov     ecx, eax; dwBytes
0x18000b15f  xor     ebx, ebx
0x18000b161  call    AllocWLMem
0x18000b166  mov     rbp, rax
0x18000b169  test    rax, rax
0x18000b16c  jnz     short loc_18000B184
0x18000b16e  call    cs:__imp_GetLastError
0x18000b175  nop     dword ptr [rax+rax+00h]
0x18000b17a  mov     ebx, eax
0x18000b17c  test    eax, eax
0x18000b17e  jnz     loc_18000B20B
0x18000b184  mov     [rdi], rbp
0x18000b187  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b18e  cmp     rcx, r12
0x18000b191  jz      short loc_18000B19D
0x18000b193  test    byte ptr [rcx+1Ch], 10h
0x18000b197  jnz     loc_18000B242
0x18000b19d  test    ebx, ebx
0x18000b19f  jnz     loc_18000B266
0x18000b1a5  mov     rax, [rdi]
0x18000b1a8  mov     [rax+10h], r15d
0x18000b1ac  mov     rax, [rdi]
0x18000b1af  mov     [rax+20h], esi
0x18000b1b2  mov     rax, [rdi]
0x18000b1b5  mov     [rax+18h], r14
0x18000b1b9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b1c0  cmp     rcx, r12
0x18000b1c3  jz      short loc_18000B1D2
0x18000b1c5  test    dword ptr [rcx+44h], 100h
0x18000b1cc  jnz     loc_18000B296
0x18000b1d2  mov     eax, ebx
0x18000b1d4  add     rsp, 20h
0x18000b1d8  pop     r15
0x18000b1da  pop     r14
0x18000b1dc  pop     r12
0x18000b1de  pop     rdi
0x18000b1df  pop     rsi
0x18000b1e0  pop     rbp
0x18000b1e1  pop     rbx
0x18000b1e2  retn
0x18000b1e4  mov     eax, esi
0x18000b1e6  shl     eax, 4
0x18000b1e9  add     eax, 28h ; '('
0x18000b1ec  jmp     loc_18000B15D
0x18000b1f1  mov     rcx, [rcx+38h]
0x18000b1f5  lea     r8, WPP_4b473b0d41083bd40dfc61d99b047aaf_Traceguids
0x18000b1fc  mov     edx, 0Ah
0x18000b201  call    WPP_SF_
0x18000b206  jmp     loc_18000B152
0x18000b20b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b212  cmp     rcx, r12
0x18000b215  jz      loc_18000B184
0x18000b21b  test    byte ptr [rcx+1Ch], 1
0x18000b21f  jz      loc_18000B184
0x18000b225  mov     rcx, [rcx+10h]
0x18000b229  lea     r8, WPP_13d7b2876eef3b3479d595a943243812_Traceguids
0x18000b230  mov     edx, 0Ah
0x18000b235  mov     r9d, eax
0x18000b238  call    WPP_SF_d
0x18000b23d  jmp     loc_18000B184
0x18000b242  mov     rcx, [rcx+10h]
0x18000b246  lea     r8, WPP_13d7b2876eef3b3479d595a943243812_Traceguids
0x18000b24d  mov     edx, 0Bh
0x18000b252  mov     r9, rbp
0x18000b255  call    WPP_SF_q
0x18000b25a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b261  jmp     loc_18000B19D
0x18000b266  cmp     rcx, r12
0x18000b269  jz      loc_18000B1D2
0x18000b26f  test    byte ptr [rcx+44h], 1
0x18000b273  jz      loc_18000B1C0
0x18000b279  mov     rcx, [rcx+38h]
0x18000b27d  lea     r8, WPP_4b473b0d41083bd40dfc61d99b047aaf_Traceguids
0x18000b284  mov     edx, 0Bh
0x18000b289  mov     r9d, ebx
0x18000b28c  call    WPP_SF_d
0x18000b291  jmp     loc_18000B1B9
0x18000b296  mov     rcx, [rcx+38h]
0x18000b29a  lea     r8, WPP_4b473b0d41083bd40dfc61d99b047aaf_Traceguids
0x18000b2a1  mov     edx, 0Ch
0x18000b2a6  mov     r9d, ebx
0x18000b2a9  call    WPP_SF_d
0x18000b2ae  jmp     loc_18000B1D2
```
