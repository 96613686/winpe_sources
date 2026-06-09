# GetInstance

- ea: `0x180009d14`
- end: `0x180009e19`
- name: `GetInstance`
- size: `261`
- prototype: `void __stdcall(LPSPropValue lpPropMv, LPSPropValue lpPropSv, ULONG uliInst)`
- caller_count: `15`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800027d8`
- `0x180002dd0`
- `0x180003a20`
- `0x180004300`
- `0x1800080a4`
- `0x180008230`
- `0x1800084c0`
- `0x1800094a8`
- `0x18000a820`
- `0x18000aa60`
- `0x18000ac20`
- `0x18000aef0`
- `0x18000b440`
- `0x18000c560`
- `0x18000cf90`

## callees

- `0x180004920`
- `0x180009d14`
- `0x18001f734`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x180009d8d`
- `KERNEL32!HeapAlloc` at `0x180009d8d`
- `KERNEL32!GetProcessHeap` at `0x180009d79`
- `KERNEL32!GetProcessHeap` at `0x180009d79`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
void __stdcall GetInstance(LPSPropValue lpPropMv, LPSPropValue lpPropSv, ULONG uliInst)
{
  __int64 *v3; // rbx
  __int64 **v4; // r14
  int v5; // ebp
  __int64 *v6; // rdi
  HANDLE ProcessHeap; // rax
  GUID *v8; // rax
  GUID *v9; // rdx
  __int64 **v10; // rcx

  v3 = (__int64 *)qword_18002BD08[0];
  v4 = *(__int64 ***)&uliInst;
  v5 = (unsigned __int16)lpPropMv;
  while ( 1 )
  {
    if ( v3 == qword_18002BD08 )
      goto LABEL_7;
    v6 = v3 - 1;
    if ( *((_WORD *)v3 - 2) >= (unsigned __int16)lpPropMv )
      break;
    v3 = (__int64 *)*v3;
  }
  if ( *((_WORD *)v3 - 2) == (_WORD)lpPropMv )
  {
LABEL_16:
    *v4 = v6;
    return;
  }
LABEL_7:
  if ( (_DWORD)lpPropSv )
  {
    if ( !(unsigned int)RtmReadInstanceConfig() )
    {
      ProcessHeap = GetProcessHeap();
      v8 = (GUID *)HeapAlloc(ProcessHeap, 8u, 0x40u);
      v6 = (__int64 *)v8;
      if ( v8 )
      {
        _InterlockedIncrement((volatile signed __int32 *)v8);
        v8->Data2 = v5;
        v9 = v8 + 3;
        if ( (_WORD)v5 )
        {
          if ( (unsigned int)NsiGetRoutingDomainIdForCompartment(v5 + 1, v9) )
            return;
        }
        else
        {
          *v9 = 0;
        }
        ++HIDWORD(qword_18002BD00);
        v6[2] = (__int64)(v6 + 1);
        v6[1] = (__int64)(v6 + 1);
        v6[5] = (__int64)(v6 + 4);
        v6[4] = (__int64)(v6 + 4);
        *((_DWORD *)v6 + 6) = 0;
        v10 = (__int64 **)v3[1];
        if ( *v10 != v3 )
          __fastfail(3u);
        v6[1] = (__int64)v3;
        v6[2] = (__int64)v10;
        *v10 = v6 + 1;
        v3[1] = (__int64)(v6 + 1);
        goto LABEL_16;
      }
    }
  }
}

```

## disassembly

```asm
0x180009d14  push    rbx
0x180009d16  push    rbp
0x180009d17  push    rsi
0x180009d18  push    rdi
0x180009d19  push    r14
0x180009d1b  push    r15
0x180009d1d  sub     rsp, 28h
0x180009d21  mov     rbx, cs:qword_18002BD08
0x180009d28  lea     rax, qword_18002BD08
0x180009d2f  mov     r14, r8
0x180009d32  movzx   ebp, cx
0x180009d35  xor     r15d, r15d
0x180009d38  jmp     short loc_180009D47
0x180009d3a  lea     rdi, [rbx-8]
0x180009d3e  cmp     [rdi+4], bp
0x180009d42  jnb     short loc_180009D4E
0x180009d44  mov     rbx, [rbx]
0x180009d47  cmp     rbx, rax
0x180009d4a  jnz     short loc_180009D3A
0x180009d4c  jmp     short loc_180009D54
0x180009d4e  jz      loc_180009E04
0x180009d54  test    edx, edx
0x180009d56  jnz     short loc_180009D62
0x180009d58  mov     esi, 490h
0x180009d5d  jmp     loc_180009E0A
0x180009d62  lea     rdx, [rsp+58h+arg_0]
0x180009d67  movzx   ecx, bp
0x180009d6a  call    RtmReadInstanceConfig
0x180009d6f  mov     esi, eax
0x180009d71  test    eax, eax
0x180009d73  jnz     loc_180009E0A
0x180009d79  call    cs:__imp_GetProcessHeap
0x180009d7f  mov     esi, 8
0x180009d84  mov     rcx, rax; hHeap
0x180009d87  mov     edx, esi; dwFlags
0x180009d89  lea     r8d, [rsi+38h]; dwBytes
0x180009d8d  call    cs:__imp_HeapAlloc
0x180009d93  mov     rdi, rax
0x180009d96  test    rax, rax
0x180009d99  jz      short loc_180009E0A
0x180009d9b  lock inc dword ptr [rax]
0x180009d9e  mov     [rax+4], bp
0x180009da2  lea     rdx, [rax+30h]
0x180009da6  xorps   xmm0, xmm0
0x180009da9  test    bp, bp
0x180009dac  jnz     short loc_180009DB4
0x180009dae  movdqu  xmmword ptr [rdx], xmm0
0x180009db2  jmp     short loc_180009DC2
0x180009db4  lea     ecx, [rbp+1]
0x180009db7  call    NsiGetRoutingDomainIdForCompartment
0x180009dbc  mov     esi, eax
0x180009dbe  test    eax, eax
0x180009dc0  jnz     short loc_180009E0A
0x180009dc2  inc     dword ptr cs:qword_18002BD00+4
0x180009dc8  lea     rax, [rdi+8]
0x180009dcc  mov     [rax+8], rax
0x180009dd0  mov     [rax], rax
0x180009dd3  lea     rax, [rdi+20h]
0x180009dd7  mov     [rax+8], rax
0x180009ddb  mov     [rax], rax
0x180009dde  mov     [rdi+18h], r15d
0x180009de2  mov     rcx, [rbx+8]
0x180009de6  cmp     [rcx], rbx
0x180009de9  jz      short loc_180009DF2
0x180009deb  mov     ecx, 3
0x180009df0  int     29h; Win8: RtlFailFast(ecx)
0x180009df2  lea     rax, [rdi+8]
0x180009df6  mov     [rax], rbx
0x180009df9  mov     [rax+8], rcx
0x180009dfd  mov     [rcx], rax
0x180009e00  mov     [rbx+8], rax
0x180009e04  mov     esi, r15d
0x180009e07  mov     [r14], rdi
0x180009e0a  mov     eax, esi
0x180009e0c  add     rsp, 28h
0x180009e10  pop     r15
0x180009e12  pop     r14
0x180009e14  pop     rdi
0x180009e15  pop     rsi
0x180009e16  pop     rbp
0x180009e17  pop     rbx
0x180009e18  retn
```
