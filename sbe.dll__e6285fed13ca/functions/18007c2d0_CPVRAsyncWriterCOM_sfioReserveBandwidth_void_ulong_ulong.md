# CPVRAsyncWriterCOM::sfioReserveBandwidth(void *,ulong *,ulong *)

- ea: `0x18007c2d0`
- end: `0x18007c3a1`
- name: `?sfioReserveBandwidth@CPVRAsyncWriterCOM@@AEAAHPEAXPEAK1@Z`
- size: `209`
- prototype: `int(CPVRAsyncWriterCOM *__hidden this, void *, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18007b960`

## callees

- `0x180001c00`
- `0x18002bf70`
- `0x18007c2d0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18007c375`
- `KERNEL32!GetLastError` at `0x18007c375`
- `KERNEL32!SetFileBandwidthReservation` at `0x18007c336`
- `KERNEL32!SetFileBandwidthReservation` at `0x18007c336`
- `KERNEL32!SetLastError` at `0x18007c382`
- `KERNEL32!SetLastError` at `0x18007c382`

## pseudocode

```c
__int64 __fastcall CPVRAsyncWriterCOM::sfioReserveBandwidth(
        CPVRAsyncWriterCOM *this,
        void *a2,
        unsigned int *a3,
        unsigned int *a4)
{
  DWORD v5; // edx
  DWORD v9; // r8d
  unsigned int v10; // ebx
  unsigned int v11; // eax
  unsigned int v12; // eax
  unsigned int v13; // eax
  unsigned int v14; // r9d
  DWORD v16; // [rsp+30h] [rbp-38h] BYREF
  DWORD v17; // [rsp+34h] [rbp-34h] BYREF

  v16 = 0;
  v5 = *((_DWORD *)this + 38);
  v17 = 0;
  if ( v5 == -1 || (v9 = *((_DWORD *)this + 39), v9 == -1) )
  {
    v10 = 0;
    SetLastError(0xDu);
  }
  else
  {
    v10 = SetFileBandwidthReservation(a2, v5, v9, 0, &v16, &v17);
    if ( v10 )
    {
      v11 = AlignUp<unsigned long>(v16, *((unsigned int *)this + 4));
      v12 = AlignUp<unsigned long>(*((unsigned int *)this + 2), v11);
      *a3 = v12;
      v13 = AlignUp<unsigned long>((unsigned int)(*((_DWORD *)this + 2) * *((_DWORD *)this + 3)), v12);
      *a4 = v13 / v14;
    }
    else
    {
      GetLastError();
    }
  }
  return v10;
}

```

## disassembly

```asm
0x18007c2d0  mov     r11, rsp
0x18007c2d3  push    rbx
0x18007c2d4  push    rsi
0x18007c2d5  push    rdi
0x18007c2d6  push    r14
0x18007c2d8  sub     rsp, 48h
0x18007c2dc  mov     rax, cs:__security_cookie
0x18007c2e3  xor     rax, rsp
0x18007c2e6  mov     [rsp+68h+var_30], rax
0x18007c2eb  mov     rax, rdx
0x18007c2ee  mov     [rsp+68h+var_38], 0
0x18007c2f6  mov     edx, [rcx+98h]; nPeriodMilliseconds
0x18007c2fc  mov     rdi, rcx
0x18007c2ff  or      ecx, 0FFFFFFFFh
0x18007c302  mov     [rsp+68h+var_34], 0
0x18007c30a  mov     r14, r9
0x18007c30d  mov     rsi, r8
0x18007c310  cmp     edx, ecx
0x18007c312  jz      short loc_18007C37D
0x18007c314  mov     r8d, [rdi+9Ch]; nBytesPerPeriod
0x18007c31b  cmp     r8d, ecx
0x18007c31e  jz      short loc_18007C37D
0x18007c320  lea     rcx, [r11-34h]
0x18007c324  xor     r9d, r9d; bDiscardable
0x18007c327  mov     [r11-40h], rcx
0x18007c32b  lea     rcx, [r11-38h]
0x18007c32f  mov     [r11-48h], rcx
0x18007c333  mov     rcx, rax; hFile
0x18007c336  call    cs:__imp_SetFileBandwidthReservation
0x18007c33c  mov     ebx, eax
0x18007c33e  test    eax, eax
0x18007c340  jz      short loc_18007C375
0x18007c342  mov     edx, [rdi+10h]
0x18007c345  mov     ecx, [rsp+68h+var_38]
0x18007c349  call    ??$AlignUp@K@@YAKKK@Z; AlignUp<ulong>(ulong,ulong)
0x18007c34e  mov     ecx, [rdi+8]
0x18007c351  mov     edx, eax
0x18007c353  call    ??$AlignUp@K@@YAKKK@Z; AlignUp<ulong>(ulong,ulong)
0x18007c358  mov     [rsi], eax
0x18007c35a  mov     edx, eax
0x18007c35c  mov     ecx, [rdi+0Ch]
0x18007c35f  mov     r9d, eax
0x18007c362  imul    ecx, [rdi+8]
0x18007c366  call    ??$AlignUp@K@@YAKKK@Z; AlignUp<ulong>(ulong,ulong)
0x18007c36b  xor     edx, edx
0x18007c36d  div     r9d
0x18007c370  mov     [r14], eax
0x18007c373  jmp     short loc_18007C388
0x18007c375  call    cs:__imp_GetLastError
0x18007c37b  jmp     short loc_18007C388
0x18007c37d  xor     ebx, ebx
0x18007c37f  lea     ecx, [rbx+0Dh]; dwErrCode
0x18007c382  call    cs:__imp_SetLastError
0x18007c388  mov     eax, ebx
0x18007c38a  mov     rcx, [rsp+68h+var_30]
0x18007c38f  xor     rcx, rsp; StackCookie
0x18007c392  call    __security_check_cookie
0x18007c397  add     rsp, 48h
0x18007c39b  pop     r14
0x18007c39d  pop     rdi
0x18007c39e  pop     rsi
0x18007c39f  pop     rbx
0x18007c3a0  retn
```
