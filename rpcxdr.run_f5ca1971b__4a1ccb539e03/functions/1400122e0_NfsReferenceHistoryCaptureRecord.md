# NfsReferenceHistoryCaptureRecord

- ea: `0x1400122e0`
- end: `0x1400123b0`
- name: `NfsReferenceHistoryCaptureRecord`
- size: `208`
- prototype: ``
- caller_count: `17`
- callee_count: `3`
- tags: ``

## callers

- `0x140002170`
- `0x1400021b0`
- `0x14000f770`
- `0x1400128ac`
- `0x140012950`
- `0x1400129c4`
- `0x140012a60`
- `0x140013044`
- `0x14001318c`
- `0x1400137cc`
- `0x140013828`
- `0x1400139e4`
- `0x140013af8`
- `0x140013b78`
- `0x140013de4`
- `0x1400150f0`
- `0x1400151b0`

## callees

- `0x1400122e0`
- `0x140014e54`
- `0x140015b40`

## import_xrefs

- `ntoskrnl!RtlCaptureStackBackTrace` at `0x140012372`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x140012372`

## pseudocode

```c
__int64 __fastcall NfsReferenceHistoryCaptureRecord(_DWORD *a1, unsigned int a2, unsigned int a3)
{
  _QWORD *v3; // rbx
  unsigned int v7; // ecx
  unsigned int v8; // r9d
  __int64 i; // rdx
  _QWORD v11[17]; // [rsp+20h] [rbp-88h] BYREF

  v3 = NfsRefHistoryTracingpGlobal;
  memset(v11, 0, 0x60u);
  if ( NfsRefHistoryTracingpGlobal )
  {
    v7 = 0;
    if ( *a1 != 1128616530 )
    {
      v8 = *((_DWORD *)NfsRefHistoryTracingpGlobal + 2);
      if ( v8 )
      {
        for ( i = 0; (unsigned int)i < v8; i = (unsigned int)(i + 1) )
        {
          if ( *((_DWORD *)NfsRefHistoryTracingpGlobal + i + 3) == *a1 )
            goto LABEL_9;
        }
      }
      else
      {
LABEL_9:
        LODWORD(v11[2]) = *a1;
        v11[0] = __PAIR64__(a3, a2);
        v11[1] = a1;
        v11[3] = KeGetCurrentThread();
        HIDWORD(v11[2]) = RtlCaptureStackBackTrace(4u, 8u, (PVOID *)&v11[4], 0);
        if ( *(_DWORD *)(*v3 + 20LL) == 96 )
          return (unsigned int)NfsHistoryAddRecordInHistory(*v3, v11);
        else
          return (unsigned int)-1073741788;
      }
    }
  }
  else
  {
    return (unsigned int)-1073741811;
  }
  return v7;
}

```

## disassembly

```asm
0x1400122e0  push    rbx
0x1400122e2  push    rbp
0x1400122e3  push    rsi
0x1400122e4  push    rdi
0x1400122e5  sub     rsp, 88h
0x1400122ec  mov     rbx, cs:NfsRefHistoryTracingpGlobal
0x1400122f3  mov     ebp, edx
0x1400122f5  xor     edx, edx; Val
0x1400122f7  mov     esi, r8d
0x1400122fa  mov     rdi, rcx
0x1400122fd  lea     rcx, [rsp+0A8h+var_88]; void *
0x140012302  lea     r8d, [rdx+60h]; Size
0x140012306  call    memset
0x14001230b  test    rbx, rbx
0x14001230e  jnz     short loc_14001231A
0x140012310  mov     ecx, 0C000000Dh
0x140012315  jmp     loc_1400123A1
0x14001231a  mov     r8d, [rdi]
0x14001231d  xor     ecx, ecx
0x14001231f  cmp     r8d, 43455252h
0x140012326  jz      short loc_1400123A1
0x140012328  mov     r9d, [rbx+8]
0x14001232c  test    r9d, r9d
0x14001232f  jz      short loc_140012343
0x140012331  xor     edx, edx
0x140012333  cmp     edx, r9d
0x140012336  jnb     short loc_1400123A1
0x140012338  cmp     [rbx+rdx*4+0Ch], r8d
0x14001233d  jz      short loc_140012343
0x14001233f  inc     edx
0x140012341  jmp     short loc_140012333
0x140012343  mov     [rsp+0A8h+var_78], r8d
0x140012348  xor     r9d, r9d; BackTraceHash
0x14001234b  mov     [rsp+0A8h+var_88], ebp
0x14001234f  lea     r8, [rsp+0A8h+BackTrace]; BackTrace
0x140012354  mov     [rsp+0A8h+var_84], esi
0x140012358  mov     [rsp+0A8h+var_80], rdi
0x14001235d  mov     rax, gs:188h
0x140012366  lea     edx, [r9+8]; FramesToCapture
0x14001236a  lea     ecx, [rdx-4]; FramesToSkip
0x14001236d  mov     [rsp+0A8h+var_70], rax
0x140012372  call    cs:__imp_RtlCaptureStackBackTrace
0x140012379  nop     dword ptr [rax+rax+00h]
0x14001237e  movzx   eax, ax
0x140012381  mov     [rsp+0A8h+var_74], eax
0x140012385  mov     rcx, [rbx]
0x140012388  cmp     dword ptr [rcx+14h], 60h ; '`'
0x14001238c  jz      short loc_140012395
0x14001238e  mov     ecx, 0C0000024h
0x140012393  jmp     short loc_1400123A1
0x140012395  lea     rdx, [rsp+0A8h+var_88]
0x14001239a  call    NfsHistoryAddRecordInHistory
0x14001239f  mov     ecx, eax
0x1400123a1  mov     eax, ecx
0x1400123a3  add     rsp, 88h
0x1400123aa  pop     rdi
0x1400123ab  pop     rsi
0x1400123ac  pop     rbp
0x1400123ad  pop     rbx
0x1400123ae  retn
```
