# CSsl3TlsContext::QueryEapKeyBlock(void *)

- ea: `0x1800600d4`
- end: `0x1800601ff`
- name: `?QueryEapKeyBlock@CSsl3TlsContext@@AEAAKPEAX@Z`
- size: `299`
- prototype: `unsigned int __fastcall(CSsl3TlsContext *__hidden this, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180046b00`

## callees

- `0x1800597b0`
- `0x18005a160`
- `0x1800600d4`
- `0x180091010`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x18006013f`
- `ntdll!RtlReleaseResource` at `0x1800601ab`
- `ntdll!RtlReleaseResource` at `0x18006013f`
- `ntdll!RtlReleaseResource` at `0x1800601ab`
- `ntdll!RtlAcquireResourceShared` at `0x180060124`
- `ntdll!RtlAcquireResourceShared` at `0x180060124`
- `ncrypt!SslComputeEapKeyBlock` at `0x180060197`
- `ncrypt!SslComputeEapKeyBlock` at `0x180060197`

## pseudocode

```c
__int64 __fastcall CSsl3TlsContext::QueryEapKeyBlock(CSsl3TlsContext *this, void *a2)
{
  __int64 v4; // rax
  __int64 v5; // rcx
  __int64 v6; // r10
  __int64 *v8; // rax
  __int64 v9; // rcx
  int v10; // ebx
  unsigned int v11[4]; // [rsp+40h] [rbp-E8h] BYREF
  _BYTE v12[192]; // [rsp+50h] [rbp-D8h] BYREF

  memset_0(v12, 0, sizeof(v12));
  v4 = *((_QWORD *)this + 14);
  v11[0] = 192;
  RtlAcquireResourceShared((PRTL_RESOURCE)(*(_QWORD *)(v4 + 40) + 80LL), 1u);
  v5 = *((_QWORD *)this + 14);
  v6 = *(_QWORD *)(v5 + 32);
  if ( v6 )
  {
    v8 = (__int64 *)*((_QWORD *)this + 1);
    if ( v8 )
      v9 = *v8;
    else
      v9 = 0;
    v10 = SslComputeEapKeyBlock(v9, v6, (char *)this + 1992, 64, v12, v11[0], v11, *((_DWORD *)this + 514));
    RtlReleaseResource((PRTL_RESOURCE)(*(_QWORD *)(*((_QWORD *)this + 14) + 40LL) + 80LL));
    if ( v10 )
      return 1359;
    else
      return (*(__int64 (__fastcall **)(_QWORD, _QWORD, void *, _BYTE *))(LsaTable + 72))(0, v11[0], a2, v12);
  }
  else
  {
    RtlReleaseResource((PRTL_RESOURCE)(*(_QWORD *)(v5 + 40) + 80LL));
    return 2148074241LL;
  }
}

```

## disassembly

```asm
0x1800600d4  mov     [rsp+arg_10], rbx
0x1800600d9  mov     [rsp+arg_18], rsi
0x1800600de  push    rdi
0x1800600df  sub     rsp, 120h
0x1800600e6  mov     rax, cs:__security_cookie
0x1800600ed  xor     rax, rsp
0x1800600f0  mov     [rsp+128h+var_18], rax
0x1800600f8  mov     rsi, rdx
0x1800600fb  mov     rdi, rcx
0x1800600fe  mov     ebx, 0C0h
0x180060103  lea     rcx, [rsp+128h+var_D8]; void *
0x180060108  mov     r8d, ebx; Size
0x18006010b  xor     edx, edx; Val
0x18006010d  call    memset_0
0x180060112  mov     rax, [rdi+70h]
0x180060116  mov     dl, 1; Wait
0x180060118  mov     [rsp+128h+var_E8], ebx
0x18006011c  mov     rcx, [rax+28h]
0x180060120  add     rcx, 50h ; 'P'; Resource
0x180060124  call    cs:__imp_RtlAcquireResourceShared
0x18006012a  mov     rcx, [rdi+70h]
0x18006012e  mov     r10, [rcx+20h]
0x180060132  test    r10, r10
0x180060135  jnz     short loc_18006014F
0x180060137  mov     rcx, [rcx+28h]
0x18006013b  add     rcx, 50h ; 'P'; Resource
0x18006013f  call    cs:__imp_RtlReleaseResource
0x180060145  mov     eax, 80090301h
0x18006014a  jmp     loc_1800601DA
0x18006014f  mov     rax, [rdi+8]
0x180060153  mov     edx, [rdi+808h]
0x180060159  mov     r9d, [rsp+128h+var_E8]
0x18006015e  test    rax, rax
0x180060161  jz      short loc_180060168
0x180060163  mov     rcx, [rax]
0x180060166  jmp     short loc_18006016A
0x180060168  xor     ecx, ecx
0x18006016a  mov     [rsp+128h+var_F0], edx
0x18006016e  lea     rax, [rsp+128h+var_E8]
0x180060173  mov     [rsp+128h+var_F8], rax
0x180060178  lea     r8, [rdi+7C8h]
0x18006017f  mov     [rsp+128h+var_100], r9d
0x180060184  lea     rax, [rsp+128h+var_D8]
0x180060189  mov     r9d, 40h ; '@'
0x18006018f  mov     [rsp+128h+var_108], rax
0x180060194  mov     rdx, r10
0x180060197  call    cs:__imp_SslComputeEapKeyBlock
0x18006019d  mov     rcx, [rdi+70h]
0x1800601a1  mov     ebx, eax
0x1800601a3  mov     rcx, [rcx+28h]
0x1800601a7  add     rcx, 50h ; 'P'; Resource
0x1800601ab  call    cs:__imp_RtlReleaseResource
0x1800601b1  test    ebx, ebx
0x1800601b3  jz      short loc_1800601BC
0x1800601b5  mov     eax, 54Fh
0x1800601ba  jmp     short loc_1800601DA
0x1800601bc  mov     rax, cs:LsaTable
0x1800601c3  lea     r9, [rsp+128h+var_D8]
0x1800601c8  mov     edx, [rsp+128h+var_E8]
0x1800601cc  mov     r8, rsi
0x1800601cf  xor     ecx, ecx
0x1800601d1  mov     rax, [rax+48h]
0x1800601d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800601da  mov     rcx, [rsp+128h+var_18]
0x1800601e2  xor     rcx, rsp; StackCookie
0x1800601e5  call    __security_check_cookie
0x1800601ea  lea     r11, [rsp+128h+var_8]
0x1800601f2  mov     rbx, [r11+20h]
0x1800601f6  mov     rsi, [r11+28h]
0x1800601fa  mov     rsp, r11
0x1800601fd  pop     rdi
0x1800601fe  retn
```
