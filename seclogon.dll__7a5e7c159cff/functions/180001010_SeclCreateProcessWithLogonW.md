# SeclCreateProcessWithLogonW

- ea: `0x180001010`
- end: `0x180001152`
- name: `SeclCreateProcessWithLogonW`
- size: `322`
- prototype: `void __fastcall(RPC_BINDING_HANDLE BindingHandle, __int64, _OWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180001010`
- `0x180001160`
- `0x180001470`
- `0x180002f70`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000105f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000105f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001049`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001049`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000112a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000112a`

## pseudocode

```c
void __fastcall SeclCreateProcessWithLogonW(RPC_BINDING_HANDLE BindingHandle, __int64 a2, _OWORD *a3)
{
  int v6; // edi
  __int128 v7; // [rsp+28h] [rbp-60h]
  __int128 v8; // [rsp+58h] [rbp-30h]
  LPVOID lpMem; // [rsp+A8h] [rbp+20h] BYREF

  lpMem = 0;
  HIDWORD(v8) = 0;
  v7 = 0;
  EnterCriticalSection(&csForProcessCount);
  if ( g_state.dwCurrentState != 4 )
  {
    v6 = 1062;
    goto LABEL_9;
  }
  if ( !GetProcessHeap() )
  {
    v6 = 8;
    goto LABEL_9;
  }
  v6 = To_SECONDARYLOGONINFOW(a2, &lpMem);
  if ( v6 )
  {
LABEL_9:
    v7 = 0;
    if ( lpMem )
      Free_SECONDARYLOGONINFOW(lpMem);
    goto LABEL_11;
  }
  SlrCreateProcessWithLogon(BindingHandle);
  if ( lpMem )
  {
    Free_SECONDARYLOGONINFOW(lpMem);
    lpMem = 0;
  }
  v6 = 0;
LABEL_11:
  *(_QWORD *)&v8 = 0;
  DWORD2(v8) = v6;
  LeaveCriticalSection(&csForProcessCount);
  *a3 = v7;
  a3[1] = v8;
}

```

## disassembly

```asm
0x180001010  mov     rax, rsp
0x180001013  mov     [rax+8], rbx
0x180001017  mov     [rax+18h], r8
0x18000101b  push    rsi
0x18000101c  push    rdi
0x18000101d  push    r14
0x18000101f  sub     rsp, 70h
0x180001023  mov     rbx, r8
0x180001026  mov     rdi, rdx
0x180001029  mov     rsi, rcx
0x18000102c  xor     r14d, r14d
0x18000102f  mov     [rax+20h], r14
0x180001033  mov     [rax-24h], r14d
0x180001037  xorps   xmm0, xmm0
0x18000103a  movups  xmmword ptr [rax-60h], xmm0
0x18000103e  movups  xmmword ptr [rax-50h], xmm0
0x180001042  lea     rcx, csForProcessCount; lpCriticalSection
0x180001049  call    cs:__imp_EnterCriticalSection
0x18000104f  cmp     cs:g_state.dwCurrentState, 4
0x180001056  jz      short loc_18000105F
0x180001058  mov     edi, 426h
0x18000105d  jmp     short loc_1800010D6
0x18000105f  call    cs:__imp_GetProcessHeap
0x180001065  test    rax, rax
0x180001068  jnz     short loc_180001071
0x18000106a  mov     edi, 8
0x18000106f  jmp     short loc_1800010D6
0x180001071  lea     rdx, [rsp+88h+lpMem]
0x180001079  mov     rcx, rdi
0x18000107c  call    To_SECONDARYLOGONINFOW
0x180001081  mov     edi, eax
0x180001083  mov     [rsp+88h+var_68], eax
0x180001087  test    eax, eax
0x180001089  jz      short loc_18000108D
0x18000108b  jmp     short loc_1800010D6
0x18000108d  lea     r8, [rsp+88h+var_60]
0x180001092  lea     rdx, [rsp+88h+lpMem]
0x18000109a  mov     rcx, rsi; BindingHandle
0x18000109d  call    SlrCreateProcessWithLogon
0x1800010a2  mov     rcx, [rsp+88h+lpMem]; lpMem
0x1800010aa  test    rcx, rcx
0x1800010ad  jz      short loc_1800010BC
0x1800010af  call    Free_SECONDARYLOGONINFOW
0x1800010b4  mov     [rsp+88h+lpMem], r14
0x1800010bc  mov     edi, [rsp+88h+var_48]
0x1800010c0  test    edi, edi
0x1800010c2  jz      short loc_1800010C6
0x1800010c4  jmp     short loc_1800010D6
0x1800010c6  jmp     short loc_1800010FB
0x1800010c8  mov     edi, eax
0x1800010ca  mov     [rsp+88h+var_68], eax
0x1800010ce  mov     rbx, [rsp+88h+arg_10]
0x1800010d6  xorps   xmm0, xmm0
0x1800010d9  xor     eax, eax
0x1800010db  movups  [rsp+88h+var_60], xmm0
0x1800010e0  mov     [rsp+88h+var_50], rax
0x1800010e5  mov     rcx, [rsp+88h+lpMem]; lpMem
0x1800010ed  test    rcx, rcx
0x1800010f0  jz      short loc_1800010F7
0x1800010f2  call    Free_SECONDARYLOGONINFOW
0x1800010f7  mov     [rsp+88h+var_48], edi
0x1800010fb  mov     rax, qword ptr [rsp+88h+var_60]
0x180001100  mov     qword ptr [rsp+88h+var_40], rax
0x180001105  mov     rax, qword ptr [rsp+88h+var_60+8]
0x18000110a  mov     qword ptr [rsp+88h+var_40+8], rax
0x18000110f  mov     eax, dword ptr [rsp+88h+var_50]
0x180001113  mov     dword ptr [rsp+88h+var_30], eax
0x180001117  mov     eax, dword ptr [rsp+88h+var_50+4]
0x18000111b  mov     dword ptr [rsp+88h+var_30+4], eax
0x18000111f  mov     dword ptr [rsp+88h+var_30+8], edi
0x180001123  lea     rcx, csForProcessCount; lpCriticalSection
0x18000112a  call    cs:__imp_LeaveCriticalSection
0x180001130  movups  xmm0, [rsp+88h+var_40]
0x180001135  movups  xmmword ptr [rbx], xmm0
0x180001138  movups  xmm1, [rsp+88h+var_30]
0x18000113d  movups  xmmword ptr [rbx+10h], xmm1
0x180001141  mov     rbx, [rsp+88h+arg_0]
0x180001149  add     rsp, 70h
0x18000114d  pop     r14
0x18000114f  pop     rdi
0x180001150  pop     rsi
0x180001151  retn
```
