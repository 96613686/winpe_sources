# UmpoSmartSuspendRundown

- ea: `0x180009198`
- end: `0x18000929c`
- name: `UmpoSmartSuspendRundown`
- size: `260`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180008c80`

## callees

- `0x180009198`
- `0x180010070`
- `0x180010946`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18000927c`
- `ntdll!EtwEventWrite` at `0x18000927c`

## pseudocode

```c
__int64 UmpoSmartSuspendRundown()
{
  __int64 v0; // r10
  __int64 v1; // rdx
  __int64 v2; // r8
  __int64 i; // r9
  int v4; // eax
  int v6; // [rsp+20h] [rbp-89h] BYREF
  _QWORD v7[8]; // [rsp+30h] [rbp-79h] BYREF
  _DWORD v8[24]; // [rsp+70h] [rbp-39h] BYREF

  memset_0(v8, 0, sizeof(v8));
  v0 = 0;
  v6 = 12;
  v1 = 0;
  do
  {
    v2 = 0;
    do
    {
      for ( i = 0; i != 2; ++i )
      {
        v8[2 * v0] = *((unsigned __int8 *)&UmpoSmartSuspendMetadata[3 * v1 + v2] + 4 * i);
        v4 = *((unsigned __int8 *)&UmpoSmartSuspendMetadata[3 * v1 + v2] + 4 * i + 1);
        v8[2 * v0 + 1] = v4;
        v0 = (unsigned int)(v0 + 1);
      }
      v2 = (unsigned int)(v2 + 1);
    }
    while ( (int)v2 < 3 );
    v1 = (unsigned int)(v1 + 1);
  }
  while ( (int)v1 < 2 );
  v7[0] = &UmpoSmartSuspendState;
  v7[3] = 4;
  v7[2] = &UmpoSmartSuspendDisableReason;
  v7[5] = 4;
  v7[4] = &v6;
  v7[6] = v8;
  v7[7] = 96;
  return EtwEventWrite(UmpoProviderHandle, ">", 4, v7);
}

```

## disassembly

```asm
0x180009198  push    rbp
0x18000919a  push    rbx
0x18000919b  push    rsi
0x18000919c  push    rdi
0x18000919d  push    r12
0x18000919f  lea     rbp, [rsp-37h]
0x1800091a4  sub     rsp, 0E0h
0x1800091ab  mov     rax, cs:__security_cookie
0x1800091b2  xor     rax, rsp
0x1800091b5  mov     [rbp+57h+var_30], rax
0x1800091b9  xor     edx, edx; Val
0x1800091bb  lea     rcx, [rbp+57h+var_90]; void *
0x1800091bf  lea     r8d, [rdx+60h]; Size
0x1800091c3  call    memset_0
0x1800091c8  xor     r10d, r10d
0x1800091cb  mov     [rsp+100h+var_E0], 0Ch
0x1800091d3  xor     edx, edx
0x1800091d5  lea     r12, UmpoSmartSuspendMetadata
0x1800091dc  lea     rcx, [rdx+rdx*2]
0x1800091e0  xor     r8d, r8d
0x1800091e3  lea     rsi, [r12+1]
0x1800091e8  lea     rdi, [r12+rcx*8]
0x1800091ec  lea     rsi, [rsi+rcx*8]
0x1800091f0  lea     r11, [rdi+r8*8]
0x1800091f4  xor     r9d, r9d
0x1800091f7  lea     rbx, [rsi+r8*8]
0x1800091fb  movzx   eax, byte ptr [r11+r9*4]
0x180009200  mov     [rbp+r10*8+57h+var_90], eax
0x180009205  movzx   eax, byte ptr [rbx+r9*4]
0x18000920a  inc     r9
0x18000920d  mov     [rbp+r10*8+57h+var_8C], eax
0x180009212  inc     r10d
0x180009215  cmp     r9, 2
0x180009219  jnz     short loc_1800091FB
0x18000921b  inc     r8d
0x18000921e  cmp     r8d, 3
0x180009222  jl      short loc_1800091F0
0x180009224  inc     edx
0x180009226  cmp     edx, r9d
0x180009229  jl      short loc_1800091DC
0x18000922b  mov     rcx, cs:UmpoProviderHandle
0x180009232  lea     r8d, [r9+2]
0x180009236  lea     rax, UmpoSmartSuspendState
0x18000923d  mov     [rbp+57h+var_C8], r8
0x180009241  mov     [rbp+57h+var_D0], rax
0x180009245  lea     r9, [rbp+57h+var_D0]
0x180009249  lea     rax, UmpoSmartSuspendDisableReason
0x180009250  mov     [rbp+57h+var_B8], r8
0x180009254  mov     [rbp+57h+var_C0], rax
0x180009258  lea     rdx, UMPO_EVT_SMART_SUSPEND_RUNDOWN; ">"
0x18000925f  lea     rax, [rsp+100h+var_E0]
0x180009264  mov     [rbp+57h+var_A8], r8
0x180009268  mov     [rbp+57h+var_B0], rax
0x18000926c  lea     rax, [rbp+57h+var_90]
0x180009270  mov     [rbp+57h+var_A0], rax
0x180009274  mov     [rbp+57h+var_98], 60h ; '`'
0x18000927c  call    cs:__imp_EtwEventWrite
0x180009282  mov     rcx, [rbp+57h+var_30]
0x180009286  xor     rcx, rsp; StackCookie
0x180009289  call    __security_check_cookie
0x18000928e  add     rsp, 0E0h
0x180009295  pop     r12
0x180009297  pop     rdi
0x180009298  pop     rsi
0x180009299  pop     rbx
0x18000929a  pop     rbp
0x18000929b  retn
```
