# THREAD_MANAGER::GetNextIdealNodeAndCpu(ulong &)

- ea: `0x180001690`
- end: `0x18000176a`
- name: `?GetNextIdealNodeAndCpu@THREAD_MANAGER@@AEAA?AU_PROCESSOR_NUMBER@@AEAK@Z`
- size: `218`
- prototype: `struct _PROCESSOR_NUMBER __fastcall(THREAD_MANAGER *__hidden this, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180001b40`

## callees

- `0x180001690`

## pseudocode

```c
unsigned int *__fastcall THREAD_MANAGER::GetNextIdealNodeAndCpu(THREAD_MANAGER *this, unsigned int *a2, _DWORD *a3)
{
  unsigned int v3; // ebx
  _DWORD *v4; // r14
  __int64 v5; // r11
  __int64 v8; // r9
  __int64 v9; // rbx
  unsigned int v10; // eax
  unsigned __int64 v11; // rcx
  unsigned int v12; // et2
  char v13; // dl
  __int64 v14; // rax
  __int16 v15; // cx
  unsigned int *result; // rax

  v3 = *((_DWORD *)this + 40);
  v4 = a3;
  v5 = *((_QWORD *)this + 19);
  v8 = 0;
  LODWORD(a3) = v3 + 1;
  do
  {
    if ( *(_BYTE *)(v5 + 24 * v8 + 16)
      && ((_DWORD)a3 == v3 + 1 || *(_DWORD *)(v5 + 24 * v8 + 20) < *(_DWORD *)(v5 + 24LL * (unsigned int)a3 + 20)) )
    {
      LODWORD(a3) = v8;
    }
    v8 = (unsigned int)(v8 + 1);
  }
  while ( (unsigned int)v8 <= v3 );
  *v4 = (_DWORD)a3;
  v9 = 24LL * (unsigned int)a3;
  v10 = *(unsigned __int8 *)(v9 + v5 + 17);
  v11 = *(_QWORD *)(v9 + v5);
  v12 = v10 % *(unsigned __int8 *)(v9 + v5 + 16);
  LOBYTE(a3) = 0;
  *(_BYTE *)(v9 + v5 + 17) = v10 + 1;
  v13 = v12 + 1;
  if ( (_BYTE)v12 != 0xFF )
  {
    do
    {
      _BitScanForward64((unsigned __int64 *)&a3, v11);
      v11 &= ~(1LL << (char)a3);
      --v13;
    }
    while ( v13 );
  }
  *a2 = 0;
  v14 = *((_QWORD *)this + 19);
  *((_BYTE *)a2 + 2) = (_BYTE)a3;
  v15 = *(_WORD *)(v14 + v9 + 8);
  result = a2;
  *(_WORD *)a2 = v15;
  return result;
}

```

## disassembly

```asm
0x180001690  push    rbx
0x180001692  push    rsi
0x180001693  push    rdi
0x180001694  push    r14
0x180001696  mov     ebx, [rcx+0A0h]
0x18000169c  mov     r14, r8
0x18000169f  mov     r11, [rcx+98h]
0x1800016a6  mov     r10, rdx
0x1800016a9  mov     rsi, rcx
0x1800016ac  xor     r9d, r9d
0x1800016af  lea     edi, [rbx+1]
0x1800016b2  mov     r8d, edi
0x1800016b5  lea     rcx, [r9+r9*2]
0x1800016b9  cmp     byte ptr [r11+rcx*8+10h], 0
0x1800016bf  lea     rdx, [r11+rcx*8]
0x1800016c3  jz      short loc_1800016E3
0x1800016c5  cmp     r8d, edi
0x1800016c8  jz      loc_180001762
0x1800016ce  mov     eax, r8d
0x1800016d1  lea     rcx, [rax+rax*2]
0x1800016d5  mov     eax, [r11+rcx*8+14h]
0x1800016da  cmp     [rdx+14h], eax
0x1800016dd  jb      loc_180001762
0x1800016e3  inc     r9d
0x1800016e6  cmp     r9d, ebx
0x1800016e9  jbe     short loc_1800016B5
0x1800016eb  mov     eax, r8d
0x1800016ee  xor     edx, edx
0x1800016f0  mov     [r14], r8d
0x1800016f3  lea     rcx, [rax+rax*2]
0x1800016f7  lea     rbx, ds:0[rcx*8]
0x1800016ff  movzx   r9d, byte ptr [rbx+r11+11h]
0x180001705  movzx   r8d, byte ptr [rbx+r11+10h]
0x18000170b  mov     eax, r9d
0x18000170e  mov     rcx, [rbx+r11]
0x180001712  inc     r9b
0x180001715  div     r8d
0x180001718  xor     r8d, r8d
0x18000171b  mov     [rbx+r11+11h], r9b
0x180001720  add     dl, 1
0x180001723  jz      short loc_180001740
0x180001725  nop     word ptr [rax+rax+00000000h]
0x180001730  bsf     r8, rcx
0x180001734  mov     eax, r8d
0x180001737  btr     rcx, rax
0x18000173b  add     dl, 0FFh
0x18000173e  jnz     short loc_180001730
0x180001740  xor     eax, eax
0x180001742  mov     [r10], eax
0x180001745  mov     rax, [rsi+98h]
0x18000174c  mov     [r10+2], r8b
0x180001750  movzx   ecx, word ptr [rax+rbx+8]
0x180001755  mov     rax, r10
0x180001758  mov     [r10], cx
0x18000175c  pop     r14
0x18000175e  pop     rdi
0x18000175f  pop     rsi
0x180001760  pop     rbx
0x180001761  retn
0x180001762  mov     r8d, r9d
0x180001765  jmp     loc_1800016E3
```
