# DlpGetServiceNameInSystemSpace

- ea: `0x140011bcc`
- end: `0x140011c7b`
- name: `DlpGetServiceNameInSystemSpace`
- size: `175`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x140011a90`
- `0x14001cb30`

## callees

- `0x140011bcc`
- `0x14006df80`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x140011be2`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140011be2`

## string_xrefs

- `0x140011c08`: `\Registry\Machine\System\CurrentControlSet\Services\DXGKrnl`

## pseudocode

```c
_OWORD *DlpGetServiceNameInSystemSpace()
{
  _OWORD *PoolWithTag; // rax
  _OWORD *v1; // rbx
  _OWORD *result; // rax

  PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)1025, 0x78u, 0x706D6C44u);
  v1 = PoolWithTag;
  if ( ExPoolZeroingNativelySupported )
  {
    if ( !PoolWithTag )
      return 0;
  }
  else
  {
    if ( !PoolWithTag )
      return 0;
    memset_0(PoolWithTag, 0, 0x78u);
  }
  result = v1;
  *v1 = *(_OWORD *)L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\DXGKrnl";
  v1[1] = *(_OWORD *)L"y\\Machine\\System\\CurrentControlSet\\Services\\DXGKrnl";
  v1[2] = *(_OWORD *)L"e\\System\\CurrentControlSet\\Services\\DXGKrnl";
  v1[3] = *(_OWORD *)L"\\CurrentControlSet\\Services\\DXGKrnl";
  v1[4] = *(_OWORD *)L"ControlSet\\Services\\DXGKrnl";
  v1[5] = *(_OWORD *)L"et\\Services\\DXGKrnl";
  v1[6] = *(_OWORD *)L"ces\\DXGKrnl";
  *((_QWORD *)v1 + 14) = *(_QWORD *)L"rnl";
  return result;
}

```

## disassembly

```asm
0x140011bcc  push    rbx
0x140011bce  sub     rsp, 20h
0x140011bd2  mov     edx, 78h ; 'x'; NumberOfBytes
0x140011bd7  mov     r8d, 706D6C44h; Tag
0x140011bdd  mov     ecx, 401h; PoolType
0x140011be2  call    cs:__imp_ExAllocatePoolWithTag
0x140011be9  nop     dword ptr [rax+rax+00h]
0x140011bee  cmp     cs:ExPoolZeroingNativelySupported, 0
0x140011bf5  mov     rbx, rax
0x140011bf8  jz      short loc_140011C66
0x140011bfa  test    rax, rax
0x140011bfd  jnz     short loc_140011C08
0x140011bff  xor     eax, eax
0x140011c01  add     rsp, 20h
0x140011c05  pop     rbx
0x140011c06  retn
0x140011c08  movaps  xmm0, xmmword ptr cs:aRegistryMachin; "\\Registry\\Machine\\System\\CurrentCon"...
0x140011c0f  mov     rax, rbx
0x140011c12  movups  xmmword ptr [rbx], xmm0
0x140011c15  movaps  xmm1, xmmword ptr cs:aRegistryMachin+10h; "y\\Machine\\System\\CurrentControlSet\\"...
0x140011c1c  movups  xmmword ptr [rbx+10h], xmm1
0x140011c20  movaps  xmm0, xmmword ptr cs:aRegistryMachin+20h; "e\\System\\CurrentControlSet\\Services"...
0x140011c27  movups  xmmword ptr [rbx+20h], xmm0
0x140011c2b  movaps  xmm1, xmmword ptr cs:aRegistryMachin+30h; "\\CurrentControlSet\\Services\\DXGKrnl"
0x140011c32  movups  xmmword ptr [rbx+30h], xmm1
0x140011c36  movaps  xmm0, xmmword ptr cs:aRegistryMachin+40h; "ControlSet\\Services\\DXGKrnl"
0x140011c3d  movups  xmmword ptr [rbx+40h], xmm0
0x140011c41  movaps  xmm1, xmmword ptr cs:aRegistryMachin+50h; "et\\Services\\DXGKrnl"
0x140011c48  movups  xmmword ptr [rbx+50h], xmm1
0x140011c4c  movaps  xmm0, xmmword ptr cs:aRegistryMachin+60h; "ces\\DXGKrnl"
0x140011c53  movups  xmmword ptr [rbx+60h], xmm0
0x140011c57  movsd   xmm1, qword ptr cs:aRegistryMachin+70h; "rnl"
0x140011c5f  movsd   qword ptr [rbx+70h], xmm1
0x140011c64  jmp     short loc_140011C01
0x140011c66  test    rbx, rbx
0x140011c69  jz      short loc_140011BFF
0x140011c6b  xor     edx, edx; Val
0x140011c6d  mov     rcx, rbx; void *
0x140011c70  lea     r8d, [rdx+78h]; Size
0x140011c74  call    memset_0
0x140011c79  jmp     short loc_140011C08
```
