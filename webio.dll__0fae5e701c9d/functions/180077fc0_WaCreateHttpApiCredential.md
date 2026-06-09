# WaCreateHttpApiCredential

- ea: `0x180077fc0`
- end: `0x1800780ed`
- name: `WaCreateHttpApiCredential`
- size: `301`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18007b514`
- `0x18007c878`

## callees

- `0x180077fc0`
- `0x180093be0`
- `0x1800971ec`
- `0x180098010`

## import_xrefs

- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x180078064`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x1800780a3`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x180078064`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x1800780a3`
- `IPHLPAPI!GetCurrentThreadCompartmentId` at `0x18007804a`
- `IPHLPAPI!GetCurrentThreadCompartmentId` at `0x18007804a`

## pseudocode

```c
__int64 __fastcall WaCreateHttpApiCredential(
        __int64 a1,
        NET_IF_COMPARTMENT_ID a2,
        unsigned __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6)
{
  int v6; // r15d
  NET_IF_COMPARTMENT_ID CurrentThreadCompartmentId; // edi
  __int16 v12; // ax
  unsigned int v13; // ebx
  NTSTATUS v14; // eax
  __int128 v16; // [rsp+40h] [rbp-58h] BYREF

  v6 = 0;
  CurrentThreadCompartmentId = 0;
  if ( (BYTE3(xmmword_1800AD720) & 4) != 0 )
  {
    v16 = a3;
    if ( a3 )
      v12 = 20;
    else
      v12 = 0;
    WORD4(v16) = v12;
    WPP_SF_q_HEX_Siq(a1, a2, a3, a1, (__int64)&v16, a4, a5, a6);
  }
  if ( !a2
    || (CurrentThreadCompartmentId = GetCurrentThreadCompartmentId(), CurrentThreadCompartmentId == a2)
    || (v6 = 1, (v13 = SetCurrentThreadCompartmentId(a2)) == 0) )
  {
    v13 = (*(__int64 (__fastcall **)(__int64, unsigned __int64, __int64, __int64, __int64))(WaHttpClientVTable + 192))(
            a1,
            a3,
            a4,
            a5,
            a6);
    if ( v6 )
    {
      v14 = SetCurrentThreadCompartmentId(CurrentThreadCompartmentId);
      if ( v14 )
        __fastfail(v14);
    }
  }
  if ( (BYTE3(xmmword_1800AD720) & 4) != 0 )
    WPP_SF_d(1050, 32, WPP_305d602a2c4b3ed688f990a0fb56ab50_Traceguids, v13);
  return v13;
}

```

## disassembly

```asm
0x180077fc0  push    rbx
0x180077fc2  push    rbp
0x180077fc3  push    rsi
0x180077fc4  push    rdi
0x180077fc5  push    r12
0x180077fc7  push    r13
0x180077fc9  push    r14
0x180077fcb  push    r15
0x180077fcd  sub     rsp, 58h
0x180077fd1  xor     r15d, r15d
0x180077fd4  mov     rbp, r9
0x180077fd7  xor     edi, edi
0x180077fd9  mov     rsi, r8
0x180077fdc  mov     ebx, edx
0x180077fde  mov     r14, rcx
0x180077fe1  test    byte ptr cs:xmmword_1800AD720+3, 4
0x180077fe8  mov     r12, [rsp+98h+arg_28]
0x180077ff0  mov     r13, [rsp+98h+arg_20]
0x180077ff8  jz      short loc_180078046
0x180077ffa  xorps   xmm0, xmm0
0x180077ffd  movups  [rsp+98h+var_58], xmm0
0x180078002  mov     qword ptr [rsp+98h+var_58], r8
0x180078007  test    r8, r8
0x18007800a  jnz     short loc_180078010
0x18007800c  xor     eax, eax
0x18007800e  jmp     short loc_180078015
0x180078010  mov     eax, 14h
0x180078015  mov     word ptr [rsp+98h+var_58+8], ax
0x18007801a  mov     r9, r14
0x18007801d  movaps  xmm0, [rsp+98h+var_58]
0x180078022  lea     rax, [rsp+98h+var_58]
0x180078027  mov     [rsp+98h+var_60], r12
0x18007802c  mov     [rsp+98h+var_68], r13
0x180078031  mov     [rsp+98h+var_70], rbp
0x180078036  movdqa  [rsp+98h+var_58], xmm0
0x18007803c  mov     [rsp+98h+var_78], rax
0x180078041  call    WPP_SF_q_HEX_Siq
0x180078046  test    ebx, ebx
0x180078048  jz      short loc_180078076
0x18007804a  call    cs:__imp_GetCurrentThreadCompartmentId
0x180078051  nop     dword ptr [rax+rax+00h]
0x180078056  mov     edi, eax
0x180078058  cmp     eax, ebx
0x18007805a  jz      short loc_180078076
0x18007805c  mov     ecx, ebx; CompartmentId
0x18007805e  mov     r15d, 1
0x180078064  call    cs:__imp_SetCurrentThreadCompartmentId
0x18007806b  nop     dword ptr [rax+rax+00h]
0x180078070  mov     ebx, eax
0x180078072  test    eax, eax
0x180078074  jnz     short loc_1800780B7
0x180078076  mov     rcx, cs:WaHttpClientVTable
0x18007807d  mov     r9, r13
0x180078080  mov     r8, rbp
0x180078083  mov     [rsp+98h+var_78], r12
0x180078088  mov     rdx, rsi
0x18007808b  mov     rax, [rcx+0C0h]
0x180078092  mov     rcx, r14
0x180078095  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007809a  mov     ebx, eax
0x18007809c  test    r15d, r15d
0x18007809f  jz      short loc_1800780B7
0x1800780a1  mov     ecx, edi; CompartmentId
0x1800780a3  call    cs:__imp_SetCurrentThreadCompartmentId
0x1800780aa  nop     dword ptr [rax+rax+00h]
0x1800780af  test    eax, eax
0x1800780b1  jz      short loc_1800780B7
0x1800780b3  mov     ecx, eax
0x1800780b5  int     29h; Win8: RtlFailFast(ecx)
0x1800780b7  test    byte ptr cs:xmmword_1800AD720+3, 4
0x1800780be  jz      short loc_1800780D9
0x1800780c0  mov     edx, 20h ; ' '
0x1800780c5  lea     r8, WPP_305d602a2c4b3ed688f990a0fb56ab50_Traceguids
0x1800780cc  mov     ecx, 41Ah
0x1800780d1  mov     r9d, ebx
0x1800780d4  call    WPP_SF_d
0x1800780d9  mov     eax, ebx
0x1800780db  add     rsp, 58h
0x1800780df  pop     r15
0x1800780e1  pop     r14
0x1800780e3  pop     r13
0x1800780e5  pop     r12
0x1800780e7  pop     rdi
0x1800780e8  pop     rsi
0x1800780e9  pop     rbp
0x1800780ea  pop     rbx
0x1800780eb  retn
```
