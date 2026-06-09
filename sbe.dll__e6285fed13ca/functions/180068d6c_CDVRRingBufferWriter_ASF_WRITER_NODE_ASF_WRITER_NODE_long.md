# CDVRRingBufferWriter::ASF_WRITER_NODE::ASF_WRITER_NODE(long *)

- ea: `0x180068d6c`
- end: `0x180068e41`
- name: `??0ASF_WRITER_NODE@CDVRRingBufferWriter@@QEAA@PEAJ@Z`
- size: `213`
- prototype: `__int64 __fastcall(CDVRRingBufferWriter::ASF_WRITER_NODE *__hidden this, int *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18006df48`

## callees

- `0x180068d6c`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x180068dc7`
- `KERNEL32!CreateEventW` at `0x180068dfe`
- `KERNEL32!CreateEventW` at `0x180068dc7`
- `KERNEL32!CreateEventW` at `0x180068dfe`
- `KERNEL32!GetLastError` at `0x180068dd6`
- `KERNEL32!GetLastError` at `0x180068e0d`
- `KERNEL32!GetLastError` at `0x180068dd6`
- `KERNEL32!GetLastError` at `0x180068e0d`

## pseudocode

```c
CDVRRingBufferWriter::ASF_WRITER_NODE *__fastcall CDVRRingBufferWriter::ASF_WRITER_NODE::ASF_WRITER_NODE(
        CDVRRingBufferWriter::ASF_WRITER_NODE *this,
        int *a2)
{
  HANDLE EventW; // rax
  signed int LastError; // eax
  HANDLE v6; // rax

  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_DWORD *)this + 20) = 0;
  *((_DWORD *)this + 27) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 2) = 0;
  EventW = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)this + 11) = EventW;
  if ( EventW )
  {
    v6 = CreateEventW(0, 1, 1, 0);
    *((_QWORD *)this + 12) = v6;
    if ( v6 )
    {
      LastError = 0;
    }
    else
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
    }
  }
  else
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    *((_QWORD *)this + 12) = 0;
  }
  if ( a2 )
    *a2 = LastError;
  return this;
}

```

## disassembly

```asm
0x180068d6c  mov     rax, rsp
0x180068d6f  mov     [rax+8], rbx
0x180068d73  mov     [rax+18h], rsi
0x180068d77  mov     [rax+10h], rdx
0x180068d7b  push    rdi
0x180068d7c  sub     rsp, 30h
0x180068d80  mov     rdi, rdx
0x180068d83  mov     rbx, rcx
0x180068d86  xor     esi, esi
0x180068d88  mov     [rcx], rsi
0x180068d8b  mov     [rcx+8], rsi
0x180068d8f  mov     [rcx+20h], rsi
0x180068d93  mov     [rcx+28h], rsi
0x180068d97  mov     [rcx+30h], rsi
0x180068d9b  mov     [rcx+38h], rsi
0x180068d9f  mov     [rcx+40h], rsi
0x180068da3  mov     [rcx+48h], rsi
0x180068da7  mov     [rcx+50h], esi
0x180068daa  mov     [rcx+6Ch], esi
0x180068dad  mov     dword ptr [rax-18h], 80004005h
0x180068db4  mov     [rcx+18h], rsi
0x180068db8  mov     [rcx+10h], rsi
0x180068dbc  xor     r9d, r9d; lpName
0x180068dbf  xor     r8d, r8d; bInitialState
0x180068dc2  lea     edx, [rsi+1]; bManualReset
0x180068dc5  xor     ecx, ecx; lpEventAttributes
0x180068dc7  call    cs:__imp_CreateEventW
0x180068dcd  mov     [rbx+58h], rax
0x180068dd1  test    rax, rax
0x180068dd4  jnz     short loc_180068DF2
0x180068dd6  call    cs:__imp_GetLastError
0x180068ddc  test    eax, eax
0x180068dde  jle     short loc_180068DE8
0x180068de0  movzx   eax, ax
0x180068de3  or      eax, 80070000h
0x180068de8  mov     [rsp+38h+var_18], eax
0x180068dec  mov     [rbx+60h], rsi
0x180068df0  jmp     short loc_180068E27
0x180068df2  xor     r9d, r9d; lpName
0x180068df5  lea     edx, [r9+1]; bManualReset
0x180068df9  xor     ecx, ecx; lpEventAttributes
0x180068dfb  mov     r8d, edx; bInitialState
0x180068dfe  call    cs:__imp_CreateEventW
0x180068e04  mov     [rbx+60h], rax
0x180068e08  test    rax, rax
0x180068e0b  jnz     short loc_180068E21
0x180068e0d  call    cs:__imp_GetLastError
0x180068e13  test    eax, eax
0x180068e15  jle     short loc_180068E23
0x180068e17  movzx   eax, ax
0x180068e1a  or      eax, 80070000h
0x180068e1f  jmp     short loc_180068E23
0x180068e21  mov     eax, esi
0x180068e23  mov     [rsp+38h+var_18], eax
0x180068e27  test    rdi, rdi
0x180068e2a  jz      short loc_180068E2E
0x180068e2c  mov     [rdi], eax
0x180068e2e  mov     rax, rbx
0x180068e31  mov     rbx, [rsp+38h+arg_0]
0x180068e36  mov     rsi, [rsp+38h+arg_10]
0x180068e3b  add     rsp, 30h
0x180068e3f  pop     rdi
0x180068e40  retn
0x1800b3d2d  push    rbp
0x1800b3d2f  sub     rsp, 20h
0x1800b3d33  mov     rbp, rdx
0x1800b3d36  mov     rcx, [rbp+48h]
0x1800b3d3a  test    rcx, rcx
0x1800b3d3d  jz      short loc_1800B3D44
0x1800b3d3f  mov     eax, [rbp+20h]
0x1800b3d42  mov     [rcx], eax
0x1800b3d44  add     rsp, 20h
0x1800b3d48  pop     rbp
0x1800b3d49  retn
```
