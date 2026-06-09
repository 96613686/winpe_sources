# StorpTelemetrySendUnitPerfData

- ea: `0x14004e19c`
- end: `0x14004eb8b`
- name: `StorpTelemetrySendUnitPerfData`
- size: `2543`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x140047738`

## callees

- `0x14001d994`
- `0x1400290b0`
- `0x14004e19c`
- `0x1400dd25c`
- `0x1400dd5e4`
- `0x1400e1bc4`
- `0x1400e42f4`
- `0x14014b400`
- `0x14014b500`
- `0x14014b800`

## import_xrefs

- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14004e2a7`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14004e2a7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004ead2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004eae8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004ead2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004eae8`
- `ntoskrnl!KeGetRecommendedSharedDataAlignment` at `0x14004e248`
- `ntoskrnl!KeGetRecommendedSharedDataAlignment` at `0x14004e256`
- `ntoskrnl!KeGetRecommendedSharedDataAlignment` at `0x14004e248`
- `ntoskrnl!KeGetRecommendedSharedDataAlignment` at `0x14004e256`
- `HAL!KeQueryPerformanceCounter` at `0x14004e299`
- `HAL!KeQueryPerformanceCounter` at `0x14004e299`

## pseudocode

```c

```

## disassembly

```asm
0x14004e19c  mov     rax, rsp
0x14004e19f  push    rbp
0x14004e1a0  push    rbx
0x14004e1a1  push    rsi
0x14004e1a2  push    rdi
0x14004e1a3  push    r12
0x14004e1a5  push    r13
0x14004e1a7  push    r14
0x14004e1a9  push    r15
0x14004e1ab  lea     rbp, [rax-1C8h]
0x14004e1b2  sub     rsp, 488h
0x14004e1b9  movaps  xmmword ptr [rax-58h], xmm6
0x14004e1bd  movaps  xmmword ptr [rax-68h], xmm7
0x14004e1c1  mov     rax, cs:__security_cookie
0x14004e1c8  xor     rax, rsp
0x14004e1cb  mov     [rbp+1C0h+var_70], rax
0x14004e1d2  mov     r14, rcx
0x14004e1d5  xor     r13d, r13d
0x14004e1d8  lea     rcx, [rbp+1C0h+var_208]; void *
0x14004e1dc  mov     qword ptr [rbp+1C0h+PerformanceFrequency], r13
0x14004e1e0  xor     edx, edx; Val
0x14004e1e2  mov     r8d, 190h; Size
0x14004e1e8  call    memset_0
0x14004e1ed  xorps   xmm6, xmm6
0x14004e1f0  xorps   xmm7, xmm7
0x14004e1f3  mov     r12d, r13d
0x14004e1f6  mov     esi, 65546152h
0x14004e1fb  movups  [rbp+1C0h+var_238], xmm6
0x14004e1ff  movups  [rbp+1C0h+var_228], xmm7
0x14004e203  cmp     [r14+948h], r13
0x14004e20a  jnz     short loc_14004E219
0x14004e20c  mov     r15d, r13d
0x14004e20f  mov     ebx, 0C0000001h
0x14004e214  jmp     loc_14004EA70
0x14004e219  mov     edx, cs:Size
0x14004e21f  mov     r8d, esi
0x14004e222  mov     r9, [r14+8]
0x14004e226  mov     ecx, 48h ; 'H'
0x14004e22b  mov     edi, dword ptr cs:qword_140177050
0x14004e231  call    RaidAllocatePool
0x14004e236  mov     r15, rax
0x14004e239  test    rax, rax
0x14004e23c  jnz     short loc_14004E248
0x14004e23e  mov     ebx, 0C0000017h
0x14004e243  jmp     loc_14004EA70
0x14004e248  call    cs:__imp_KeGetRecommendedSharedDataAlignment
0x14004e24f  nop     dword ptr [rax+rax+00h]
0x14004e254  mov     ebx, eax
0x14004e256  call    cs:__imp_KeGetRecommendedSharedDataAlignment
0x14004e25d  nop     dword ptr [rax+rax+00h]
0x14004e262  mov     r9, [r14+8]
0x14004e266  neg     ebx
0x14004e268  mov     edx, eax
0x14004e26a  mov     r8d, esi
0x14004e26d  lea     eax, [rdi+rdi*2]
0x14004e270  mov     ecx, 48h ; 'H'
0x14004e275  lea     edx, [rdx+rax*8]
0x14004e278  mov     eax, ebx
0x14004e27a  dec     edx
0x14004e27c  and     rdx, rax
0x14004e27f  call    RaidAllocatePool
0x14004e284  mov     r12, rax
0x14004e287  test    rax, rax
0x14004e28a  jz      short loc_14004E23E
0x14004e28c  cmp     cs:UseQPCTime, r13b
0x14004e293  jz      short loc_14004E2A7
0x14004e295  lea     rcx, [rbp+1C0h+PerformanceFrequency]; PerformanceFrequency
0x14004e299  call    cs:__imp_KeQueryPerformanceCounter
0x14004e2a0  nop     dword ptr [rax+rax+00h]
0x14004e2a5  jmp     short loc_14004E2B3
0x14004e2a7  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x14004e2ae  nop     dword ptr [rax+rax+00h]
0x14004e2b3  mov     rcx, rax
0x14004e2b6  mov     ebx, 1
0x14004e2bb  test    rax, rax
0x14004e2be  jle     short loc_14004E2D4
0x14004e2c0  mov     rdx, [r14+958h]
0x14004e2c7  cmp     rax, rdx
0x14004e2ca  jge     short loc_14004E2D4
0x14004e2cc  sub     rax, rdx
0x14004e2cf  sub     rax, rbx
0x14004e2d2  jmp     short loc_14004E2DE
0x14004e2d4  mov     rax, rcx
0x14004e2d7  sub     rax, [r14+958h]
0x14004e2de  cmp     cs:UseQPCTime, r13b
0x14004e2e5  jz      short loc_14004E331
0x14004e2e7  mov     r10, qword ptr [rbp+1C0h+PerformanceFrequency]
0x14004e2eb  mov     r9, r13
0x14004e2ee  test    r10, r10
0x14004e2f1  jz      short loc_14004E334
0x14004e2f3  test    rax, rax
0x14004e2f6  jz      short loc_14004E334
0x14004e2f8  xor     edx, edx
0x14004e2fa  div     r10
0x14004e2fd  mov     r9, rax
0x14004e300  imul    rax, rdx, 3E8h
0x14004e307  xor     edx, edx
0x14004e309  div     r10
0x14004e30c  mov     r8, rdx
0x14004e30f  imul    rdx, r9, 3E8h
0x14004e316  add     rdx, rax
0x14004e319  imul    r9, rdx, 2710h
0x14004e320  imul    rax, r8, 2710h
0x14004e327  xor     edx, edx
0x14004e329  div     r10
0x14004e32c  add     r9, rax
0x14004e32f  jmp     short loc_14004E334
0x14004e331  mov     r9, rax
0x14004e334  mov     cs:qword_140177068, rcx
0x14004e33b  mov     rdx, [r14+948h]; Src
0x14004e342  mov     [r14+958h], rcx
0x14004e349  mov     rcx, r15; void *
0x14004e34c  mov     r8d, cs:Size; Size
0x14004e353  mov     [rbp+1C0h+var_210], r9
0x14004e357  call    memmove
0x14004e35c  cmp     cs:g_RaidNumberProcessors, ebx
0x14004e362  mov     r8d, ebx
0x14004e365  jbe     short loc_14004E3B5
0x14004e367  mov     edx, r8d
0x14004e36a  mov     r10d, r13d
0x14004e36d  imul    edx, cs:dword_140177058
0x14004e374  add     rdx, r15
0x14004e377  test    edi, edi
0x14004e379  jz      short loc_14004E3A9
0x14004e37b  mov     r9, r13
0x14004e37e  lea     rcx, [r9+r9*2]
0x14004e382  add     r10d, ebx
0x14004e385  mov     rax, [rdx+rcx*8]
0x14004e389  add     r9, rbx
0x14004e38c  add     [r15+rcx*8], rax
0x14004e390  mov     rax, [rdx+rcx*8+8]
0x14004e395  add     [r15+rcx*8+8], rax
0x14004e39a  mov     rax, [rdx+rcx*8+10h]
0x14004e39f  add     [r15+rcx*8+10h], rax
0x14004e3a4  cmp     r10d, edi
0x14004e3a7  jb      short loc_14004E37E
0x14004e3a9  add     r8d, ebx
0x14004e3ac  cmp     r8d, cs:g_RaidNumberProcessors
0x14004e3b3  jb      short loc_14004E367
0x14004e3b5  mov     r11, [r14+960h]
0x14004e3bc  mov     rbx, r13
0x14004e3bf  mov     esi, r13d
0x14004e3c2  test    edi, edi
0x14004e3c4  jz      short loc_14004E411
0x14004e3c6  mov     r10, r13
0x14004e3c9  mov     r13d, 1
0x14004e3cf  lea     r9, [r10+r10*2]
0x14004e3d3  add     esi, r13d
0x14004e3d6  mov     r8, [r15+r9*8]
0x14004e3da  add     r10, r13
0x14004e3dd  sub     r8, [r11+r9*8]
0x14004e3e1  mov     [r12+r9*8], r8
0x14004e3e5  mov     rdx, [r15+r9*8+8]
0x14004e3ea  sub     rdx, [r11+r9*8+8]
0x14004e3ef  mov     [r12+r9*8+8], rdx
0x14004e3f4  mov     rcx, [r15+r9*8+10h]
0x14004e3f9  sub     rcx, [r11+r9*8+10h]
0x14004e3fe  lea     rax, [rdx+r8]
0x14004e402  mov     [r12+r9*8+10h], rcx
0x14004e407  add     rbx, rax
0x14004e40a  cmp     esi, edi
0x14004e40c  jb      short loc_14004E3CF
0x14004e40e  xor     r13d, r13d
0x14004e411  mov     r8d, cs:dword_140177058; Size
0x14004e418  mov     rdx, r15; Src
0x14004e41b  mov     rcx, [r14+960h]; void *
0x14004e422  call    memmove
0x14004e427  test    rbx, rbx
0x14004e42a  jz      loc_14004EA24
0x14004e430  cmp     word ptr cs:TelemetryPerfContext, r13w
0x14004e438  mov     esi, 1
0x14004e43d  mov     [rbp+1C0h+var_A8], r13
0x14004e444  jz      short loc_14004E4BD
0x14004e446  cmp     word ptr cs:TelemetryPerfContext+2, r13w
0x14004e44e  jz      short loc_14004E4BD
0x14004e450  mov     r9d, r13d
0x14004e453  test    edi, edi
0x14004e455  jz      short loc_14004E4BD
0x14004e457  cmp     r9d, cs:dword_140176FEC
0x14004e45e  jb      short loc_14004E4B5
0x14004e460  cmp     r9d, dword ptr cs:xmmword_140177010+0Ch
0x14004e467  jnb     short loc_14004E4B5
0x14004e469  movzx   ecx, word ptr cs:TelemetryPerfContext
0x14004e470  xor     edx, edx
0x14004e472  mov     eax, r9d
0x14004e475  div     ecx
0x14004e477  mov     ecx, 0Dh
0x14004e47c  cmp     eax, 0Eh
0x14004e47f  cmovnb  eax, ecx
0x14004e482  lea     r8, [rax+rax*2]
0x14004e486  mov     eax, r9d
0x14004e489  lea     rax, [rax+rax*2]
0x14004e48d  mov     rdx, [r12+rax*8]
0x14004e491  mov     rcx, [r12+rax*8+8]
0x14004e496  mov     rax, [r12+rax*8+10h]
0x14004e49b  add     [rbp+r8*8+1C0h+var_1E8], rax
0x14004e4a0  add     [rbp+r8*8+1C0h+var_1F8], rdx
0x14004e4a5  add     [rbp+r8*8+1C0h+var_1F0], rcx
0x14004e4aa  lea     rax, [rcx+rdx]
0x14004e4ae  add     [rbp+1C0h+var_A8], rax
0x14004e4b5  add     r9d, esi
0x14004e4b8  cmp     r9d, edi
0x14004e4bb  jb      short loc_14004E457
0x14004e4bd  cmp     [r14+970h], r13
0x14004e4c4  jz      loc_14004E57D
0x14004e4ca  mov     ebx, cs:g_RaidNumberProcessors
0x14004e4d0  mov     r11d, r13d
0x14004e4d3  test    ebx, ebx
0x14004e4d5  jz      short loc_14004E532
0x14004e4d7  mov     r9, qword ptr [rbp+1C0h+var_228]
0x14004e4db  mov     r10, qword ptr [rbp+1C0h+var_238+8]
0x14004e4df  mov     r8, qword ptr [rbp+1C0h+var_238]
0x14004e4e3  mov     rcx, [r14+970h]
0x14004e4ea  movzx   eax, r11w
0x14004e4ee  imul    eax, cs:dword_140177070
0x14004e4f5  mov     edx, eax
0x14004e4f7  mov     rax, [rax+rcx]
0x14004e4fb  cmp     rax, r8
0x14004e4fe  mov     [rdx+rcx], r13
0x14004e502  cmova   r8, rax
0x14004e506  add     r10, [rdx+rcx+8]
0x14004e50b  add     r9, [rdx+rcx+10h]
0x14004e510  add     r11w, si
0x14004e514  movzx   eax, r11w
0x14004e518  cmp     eax, ebx
0x14004e51a  jb      short loc_14004E4E3
0x14004e51c  mov     qword ptr [rbp+1C0h+var_238], r8
0x14004e520  mov     qword ptr [rbp+1C0h+var_228], r9
0x14004e524  movups  xmm7, [rbp+1C0h+var_228]
0x14004e528  mov     qword ptr [rbp+1C0h+var_238+8], r10
0x14004e52c  movups  xmm6, [rbp+1C0h+var_238]
0x14004e530  jmp     short loc_14004E54A
0x14004e532  movdqa  xmm0, xmm6
0x14004e536  movq    r9, xmm7
0x14004e53b  psrldq  xmm0, 8
0x14004e540  movq    r8, xmm6
0x14004e545  movq    r10, xmm0
0x14004e54a  sub     r10, [r14+980h]
0x14004e551  sub     r9, [r14+988h]
0x14004e558  movups  xmmword ptr [r14+978h], xmm6
0x14004e560  mov     [rbp+1C0h+var_88], r9
0x14004e567  movups  xmmword ptr [r14+988h], xmm7
0x14004e56f  mov     [rbp+1C0h+var_98], r8
0x14004e576  mov     [rbp+1C0h+var_90], r10
0x14004e57d  mov     rax, [r14+0A0h]
0x14004e584  test    rax, rax
0x14004e587  jz      short loc_14004E58F
0x14004e589  lea     rbx, [rax+5Ah]
0x14004e58d  jmp     short loc_14004E5B7
0x14004e58f  mov     rdx, [r14+98h]
0x14004e596  mov     rbx, r13
0x14004e599  test    rdx, rdx
0x14004e59c  jz      short loc_14004E5B7
0x14004e59e  mov     rax, [r14+18h]
0x14004e5a2  mov     rcx, [rax+250h]
0x14004e5a9  mov     eax, [rcx+0B8h]
0x14004e5af  test    al, 40h
0x14004e5b1  jz      short loc_14004E5B7
0x14004e5b3  lea     rbx, [rdx+29h]
0x14004e5b7  cmp     cs:g_StorpTraceLoggingCriticalEventEnabled, r13d
0x14004e5be  lea     rax, a128us256us512u; "128us, 256us, 512us, 1ms, 4ms, 16ms, 64"...
0x14004e5c5  mov     [rbp+1C0h+var_200], rax
0x14004e5c9  mov     [rbp+1C0h+var_A0], r12
0x14004e5d0  mov     [rbp+1C0h+var_208], 0Ch
0x14004e5d4  jnz     loc_14004EB28
0x14004e5da  cmp     cs:g_StorpTraceLoggingCriticalEventEnabledSetByRegistry, sil
0x14004e5e1  jnz     loc_14004EB28
0x14004e5e7  lea     rdx, [rbp+1C0h+var_210]
0x14004e5eb  mov     rcx, r14
0x14004e5ee  call    StorpTelemetryLogUnitPerfDataMeasures
0x14004e5f3  test    cs:byte_140177434, 8
0x14004e5fa  jz      loc_14004EA24
0x14004e600  mov     rsi, [r14+18h]
0x14004e604  lea     rdi, dword_140157D94
0x14004e60b  movzx   ecx, byte ptr [r14+1FAh]
0x14004e613  lea     rdx, [r14+0F2h]
0x14004e61a  test    rbx, rbx
0x14004e61d  lea     r8, [r14+0B1h]
0x14004e624  lea     r9, [r14+0A8h]
0x14004e62b  mov     rax, [rsi+1418h]
0x14004e632  lea     r10, [rsi+1408h]
0x14004e639  cmovnz  rdi, rbx
0x14004e63d  lea     r11, [r14+838h]
0x14004e644  test    rax, rax
0x14004e647  lea     rbx, qword_140155FE0
0x14004e64e  cmovnz  rbx, rax
0x14004e652  mov     eax, [r14+940h]
0x14004e659  mov     [rsp+4C0h+var_248], rax
0x14004e661  and     ecx, 1
0x14004e664  mov     rax, [rbp+1C0h+var_88]
0x14004e66b  mov     [rsp+4C0h+var_250], rax
0x14004e673  mov     rax, [rbp+1C0h+var_90]
0x14004e67a  mov     [rsp+4C0h+var_258], rax
0x14004e682  mov     rax, [rbp+1C0h+var_B0]
0x14004e689  mov     [rsp+4C0h+var_260], rax
0x14004e691  mov     rax, [rbp+1C0h+var_C8]
0x14004e698  mov     [rsp+4C0h+var_268], rax
0x14004e6a0  mov     rax, [rbp+1C0h+var_E0]
0x14004e6a7  mov     [rsp+4C0h+var_270], rax
0x14004e6af  mov     rax, [rbp+1C0h+var_F8]
  ... truncated ...
```
