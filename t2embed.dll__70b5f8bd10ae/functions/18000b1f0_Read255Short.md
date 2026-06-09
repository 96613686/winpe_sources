# Read255Short

- ea: `0x18000b1f0`
- end: `0x18000b4cd`
- name: `Read255Short`
- size: `733`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180009d40`

## callees

- `0x18000b1f0`
- `0x18000b4e0`
- `0x18001c9ec`

## import_xrefs

- `msvcrt!longjmp` at `0x18000b279`
- `msvcrt!longjmp` at `0x18000b3ab`
- `msvcrt!longjmp` at `0x18000b3c2`
- `msvcrt!longjmp` at `0x18000b3d9`
- `msvcrt!longjmp` at `0x18000b3f0`
- `msvcrt!longjmp` at `0x18000b407`
- `msvcrt!longjmp` at `0x18000b41e`
- `msvcrt!longjmp` at `0x18000b43a`
- `msvcrt!longjmp` at `0x18000b456`
- `msvcrt!longjmp` at `0x18000b472`
- `msvcrt!longjmp` at `0x18000b48e`
- `msvcrt!longjmp` at `0x18000b4aa`
- `msvcrt!longjmp` at `0x18000b4c6`
- `msvcrt!longjmp` at `0x18000b279`
- `msvcrt!longjmp` at `0x18000b3ab`
- `msvcrt!longjmp` at `0x18000b3c2`
- `msvcrt!longjmp` at `0x18000b3d9`
- `msvcrt!longjmp` at `0x18000b3f0`
- `msvcrt!longjmp` at `0x18000b407`
- `msvcrt!longjmp` at `0x18000b41e`
- `msvcrt!longjmp` at `0x18000b43a`
- `msvcrt!longjmp` at `0x18000b456`
- `msvcrt!longjmp` at `0x18000b472`
- `msvcrt!longjmp` at `0x18000b48e`
- `msvcrt!longjmp` at `0x18000b4aa`
- `msvcrt!longjmp` at `0x18000b4c6`

## pseudocode

```c
__int64 __fastcall Read255Short(__int64 a1, _QWORD *a2, _BYTE *a3, unsigned __int64 a4)
{
  __int64 v4; // rax
  unsigned __int64 v9; // r8
  __int16 v10; // ax
  _BYTE *v11; // rbx
  __int16 v12; // bp
  __int16 v13; // ax
  unsigned __int16 v14; // dx
  __int64 result; // rax
  __int64 v16; // rax
  unsigned __int64 v17; // rcx
  __int64 v18; // rax
  unsigned __int8 *v19; // rcx
  __int16 v20; // r8
  unsigned __int64 v21; // rdx
  __int16 v22; // ax

  v4 = *(_QWORD *)(a1 + 112);
  v9 = *(_QWORD *)(v4 + 16);
  if ( (unsigned __int64)a3 < v9 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs();
    longjmp((_JBTYPE *)(*(_QWORD *)(a1 + 136) + 48LL), 3362);
  }
  if ( (unsigned __int64)a3 >= v9 + *(int *)(v4 + 24) )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs();
    longjmp((_JBTYPE *)(*(_QWORD *)(a1 + 136) + 48LL), 3362);
  }
  if ( (unsigned __int64)a3 >= a4 )
    longjmp((_JBTYPE *)(*(_QWORD *)(a1 + 136) + 48LL), 3362);
  LOBYTE(v10) = *a3;
  v11 = a3 + 1;
  if ( (_BYTE)v10 == 0xFD )
  {
    v16 = *(_QWORD *)(a1 + 112);
    v17 = *(_QWORD *)(v16 + 16);
    if ( (unsigned __int64)v11 < v17 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs();
      longjmp((_JBTYPE *)(*(_QWORD *)(a1 + 136) + 48LL), 3362);
    }
    if ( (unsigned __int64)v11 >= v17 + *(int *)(v16 + 24) )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs();
      longjmp((_JBTYPE *)(*(_QWORD *)(a1 + 136) + 48LL), 3362);
    }
    if ( (unsigned __int64)v11 >= a4 )
      longjmp((_JBTYPE *)(*(_QWORD *)(a1 + 136) + 48LL), 3362);
    v18 = *(_QWORD *)(a1 + 112);
    v19 = v11 + 1;
    v20 = (unsigned __int8)*v11;
    v21 = *(_QWORD *)(v18 + 16);
    if ( (unsigned __int64)(v11 + 1) < v21 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs();
      longjmp((_JBTYPE *)(*(_QWORD *)(a1 + 136) + 48LL), 3362);
    }
    if ( (unsigned __int64)v19 >= v21 + *(int *)(v18 + 24) )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs();
      longjmp((_JBTYPE *)(*(_QWORD *)(a1 + 136) + 48LL), 3362);
    }
    if ( (unsigned __int64)v19 >= a4 )
      longjmp((_JBTYPE *)(*(_QWORD *)(a1 + 136) + 48LL), 3362);
    v11 += 2;
    v14 = *v19 | (unsigned __int16)(v20 << 8);
  }
  else
  {
    if ( (_BYTE)v10 == 0xFA )
    {
      ValidateGlyphPtr(
        a1,
        v11,
        *(_QWORD *)(*(_QWORD *)(a1 + 112) + 16LL),
        *(unsigned int *)(*(_QWORD *)(a1 + 112) + 24LL));
      if ( (unsigned __int64)v11 >= a4 )
        longjmp((_JBTYPE *)(*(_QWORD *)(a1 + 136) + 48LL), 3362);
      LOBYTE(v10) = *v11;
      v12 = -1;
      ++v11;
    }
    else
    {
      v12 = 1;
    }
    if ( (_BYTE)v10 == 0xFF )
    {
      ValidateGlyphPtr(
        a1,
        v11,
        *(_QWORD *)(*(_QWORD *)(a1 + 112) + 16LL),
        *(unsigned int *)(*(_QWORD *)(a1 + 112) + 24LL));
      if ( (unsigned __int64)v11 >= a4 )
        longjmp((_JBTYPE *)(*(_QWORD *)(a1 + 136) + 48LL), 3362);
      v22 = (unsigned __int8)*v11++;
      v10 = v22 + 250;
    }
    else if ( (_BYTE)v10 == 0xFE )
    {
      ValidateGlyphPtr(
        a1,
        v11,
        *(_QWORD *)(*(_QWORD *)(a1 + 112) + 16LL),
        *(unsigned int *)(*(_QWORD *)(a1 + 112) + 24LL));
      if ( (unsigned __int64)v11 >= a4 )
        longjmp((_JBTYPE *)(*(_QWORD *)(a1 + 136) + 48LL), 3362);
      v13 = (unsigned __int8)*v11++;
      v10 = v13 + 500;
    }
    else
    {
      v10 = (unsigned __int8)v10;
      if ( (unsigned __int8)v10 >= 0xFAu )
        longjmp((_JBTYPE *)(*(_QWORD *)(a1 + 136) + 48LL), 3362);
    }
    v14 = v12 * v10;
  }
  result = v14;
  *a2 = v11;
  return result;
}

```

## disassembly

```asm
0x18000b1f0  push    rbx
0x18000b1f2  push    rsi
0x18000b1f3  push    rdi
0x18000b1f4  push    r14
0x18000b1f6  sub     rsp, 28h
0x18000b1fa  mov     rax, [rcx+70h]
0x18000b1fe  mov     rbx, r8
0x18000b201  mov     rdi, r9
0x18000b204  mov     r14, rdx
0x18000b207  mov     rsi, rcx
0x18000b20a  mov     r8, [rax+10h]
0x18000b20e  cmp     rbx, r8
0x18000b211  jb      loc_18000B425
0x18000b217  movsxd  rax, dword ptr [rax+18h]
0x18000b21b  add     rax, r8
0x18000b21e  cmp     rbx, rax
0x18000b221  jnb     loc_18000B441
0x18000b227  cmp     rbx, r9
0x18000b22a  jnb     loc_18000B39B
0x18000b230  movzx   eax, byte ptr [rbx]
0x18000b233  inc     rbx
0x18000b236  mov     [rsp+48h+arg_0], rbp
0x18000b23b  cmp     al, 0FDh
0x18000b23d  jz      loc_18000B2CC
0x18000b243  cmp     al, 0FAh
0x18000b245  jz      loc_18000B33F
0x18000b24b  mov     ebp, 1
0x18000b250  cmp     al, 0FFh
0x18000b252  jz      loc_18000B36C
0x18000b258  cmp     al, 0FEh
0x18000b25a  jz      short loc_18000B280
0x18000b25c  movzx   eax, al
0x18000b25f  mov     ecx, 0FAh
0x18000b264  cmp     ax, cx
0x18000b267  jb      short loc_18000B2AE
0x18000b269  mov     rcx, [rsi+88h]
0x18000b270  mov     edx, 0D22h; Value
0x18000b275  add     rcx, 30h ; '0'; Buf
0x18000b279  call    cs:__imp_longjmp
0x18000b280  mov     r8, [rsi+70h]
0x18000b284  mov     rdx, rbx
0x18000b287  mov     rcx, rsi
0x18000b28a  mov     r9d, [r8+18h]
0x18000b28e  mov     r8, [r8+10h]
0x18000b292  call    ValidateGlyphPtr
0x18000b297  cmp     rbx, rdi
0x18000b29a  jnb     loc_18000B40E
0x18000b2a0  movzx   eax, byte ptr [rbx]
0x18000b2a3  mov     ecx, 1F4h
0x18000b2a8  inc     rbx
0x18000b2ab  add     ax, cx
0x18000b2ae  movsx   ecx, bp
0x18000b2b1  movsx   edx, ax
0x18000b2b4  imul    edx, ecx
0x18000b2b7  mov     rbp, [rsp+48h+arg_0]
0x18000b2bc  movzx   eax, dx
0x18000b2bf  mov     [r14], rbx
0x18000b2c2  add     rsp, 28h
0x18000b2c6  pop     r14
0x18000b2c8  pop     rdi
0x18000b2c9  pop     rsi
0x18000b2ca  pop     rbx
0x18000b2cb  retn
0x18000b2cc  mov     rax, [rcx+70h]
0x18000b2d0  mov     rcx, [rax+10h]
0x18000b2d4  cmp     rbx, rcx
0x18000b2d7  jb      loc_18000B45D
0x18000b2dd  movsxd  rax, dword ptr [rax+18h]
0x18000b2e1  add     rax, rcx
0x18000b2e4  cmp     rbx, rax
0x18000b2e7  jnb     loc_18000B479
0x18000b2ed  cmp     rbx, rdi
0x18000b2f0  jnb     loc_18000B3B2
0x18000b2f6  mov     rax, [rsi+70h]
0x18000b2fa  lea     rcx, [rbx+1]
0x18000b2fe  movzx   r8d, byte ptr [rbx]
0x18000b302  mov     rdx, [rax+10h]
0x18000b306  cmp     rcx, rdx
0x18000b309  jb      loc_18000B495
0x18000b30f  movsxd  rax, dword ptr [rax+18h]
0x18000b313  add     rax, rdx
0x18000b316  cmp     rcx, rax
0x18000b319  jnb     loc_18000B4B1
0x18000b31f  cmp     rcx, rdi
0x18000b322  jnb     loc_18000B3C9
0x18000b328  movzx   eax, byte ptr [rcx]
0x18000b32b  lea     rbx, [rcx+1]
0x18000b32f  movzx   edx, r8w
0x18000b333  shl     dx, 8
0x18000b337  or      dx, ax
0x18000b33a  jmp     loc_18000B2B7
0x18000b33f  mov     r8, [rcx+70h]
0x18000b343  mov     rdx, rbx
0x18000b346  mov     r9d, [r8+18h]
0x18000b34a  mov     r8, [r8+10h]
0x18000b34e  call    ValidateGlyphPtr
0x18000b353  cmp     rbx, rdi
0x18000b356  jnb     loc_18000B3E0
0x18000b35c  movzx   eax, byte ptr [rbx]
0x18000b35f  mov     ebp, 0FFFFFFFFh
0x18000b364  inc     rbx
0x18000b367  jmp     loc_18000B250
0x18000b36c  mov     r8, [rsi+70h]
0x18000b370  mov     rdx, rbx
0x18000b373  mov     rcx, rsi
0x18000b376  mov     r9d, [r8+18h]
0x18000b37a  mov     r8, [r8+10h]
0x18000b37e  call    ValidateGlyphPtr
0x18000b383  cmp     rbx, rdi
0x18000b386  jnb     short loc_18000B3F7
0x18000b388  movzx   eax, byte ptr [rbx]
0x18000b38b  mov     ecx, 0FAh
0x18000b390  inc     rbx
0x18000b393  add     ax, cx
0x18000b396  jmp     loc_18000B2AE
0x18000b39b  mov     rcx, [rcx+88h]
0x18000b3a2  mov     edx, 0D22h; Value
0x18000b3a7  add     rcx, 30h ; '0'; Buf
0x18000b3ab  call    cs:__imp_longjmp
0x18000b3b2  mov     rcx, [rsi+88h]
0x18000b3b9  mov     edx, 0D22h; Value
0x18000b3be  add     rcx, 30h ; '0'; Buf
0x18000b3c2  call    cs:__imp_longjmp
0x18000b3c9  mov     rcx, [rsi+88h]
0x18000b3d0  mov     edx, 0D22h; Value
0x18000b3d5  add     rcx, 30h ; '0'; Buf
0x18000b3d9  call    cs:__imp_longjmp
0x18000b3e0  mov     rcx, [rsi+88h]
0x18000b3e7  mov     edx, 0D22h; Value
0x18000b3ec  add     rcx, 30h ; '0'; Buf
0x18000b3f0  call    cs:__imp_longjmp
0x18000b3f7  mov     rcx, [rsi+88h]
0x18000b3fe  mov     edx, 0D22h; Value
0x18000b403  add     rcx, 30h ; '0'; Buf
0x18000b407  call    cs:__imp_longjmp
0x18000b40e  mov     rcx, [rsi+88h]
0x18000b415  mov     edx, 0D22h; Value
0x18000b41a  add     rcx, 30h ; '0'; Buf
0x18000b41e  call    cs:__imp_longjmp
0x18000b425  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000b42a  mov     rcx, [rsi+88h]
0x18000b431  mov     edx, 0D22h; Value
0x18000b436  add     rcx, 30h ; '0'; Buf
0x18000b43a  call    cs:__imp_longjmp
0x18000b441  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000b446  mov     rcx, [rsi+88h]
0x18000b44d  mov     edx, 0D22h; Value
0x18000b452  add     rcx, 30h ; '0'; Buf
0x18000b456  call    cs:__imp_longjmp
0x18000b45d  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000b462  mov     rcx, [rsi+88h]
0x18000b469  mov     edx, 0D22h; Value
0x18000b46e  add     rcx, 30h ; '0'; Buf
0x18000b472  call    cs:__imp_longjmp
0x18000b479  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000b47e  mov     rcx, [rsi+88h]
0x18000b485  mov     edx, 0D22h; Value
0x18000b48a  add     rcx, 30h ; '0'; Buf
0x18000b48e  call    cs:__imp_longjmp
0x18000b495  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000b49a  mov     rcx, [rsi+88h]
0x18000b4a1  mov     edx, 0D22h; Value
0x18000b4a6  add     rcx, 30h ; '0'; Buf
0x18000b4aa  call    cs:__imp_longjmp
0x18000b4b1  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000b4b6  mov     rcx, [rsi+88h]
0x18000b4bd  mov     edx, 0D22h; Value
0x18000b4c2  add     rcx, 30h ; '0'; Buf
0x18000b4c6  call    cs:__imp_longjmp
```
