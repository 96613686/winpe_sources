# NtTerminateThread

- ea: `0x1400981f4`
- end: `0x14009833c`
- name: `NtTerminateThread`
- size: `328`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x140002ef0`
- `0x14000e130`
- `0x1400981f4`
- `0x140099338`
- `0x140099358`
- `0x14009b778`
- `0x1400f3620`
- `0x1400f9a80`

## pseudocode

```c
__int64 __fastcall NtTerminateThread(unsigned __int64 a1, unsigned int a2)
{
  _QWORD *StackBase; // rdi
  __int64 v5; // rcx
  __int64 result; // rax
  __int64 v7; // rbx
  int v8; // edx
  __int64 v9; // rdi
  _QWORD *v10; // [rsp+30h] [rbp-128h] BYREF
  unsigned __int64 v11; // [rsp+38h] [rbp-120h] BYREF
  signed __int32 v12[64]; // [rsp+40h] [rbp-118h] BYREF

  memset_0(v12, 0, sizeof(v12));
  StackBase = KeGetPcr()->NtTib.StackBase;
  v10 = 0;
  if ( !a1 )
  {
    v5 = *(unsigned int *)(StackBase[9] + 188LL);
    if ( (_DWORD)v5 == 1 )
      return 3221225691LL;
LABEL_11:
    LOBYTE(v5) = 1;
    SkiTerminateThread(v5, a2);
    JUMPOUT(0x14009833BLL);
  }
  result = SkobReferenceObjectByHandle(
             a1,
             *((_BYTE *)KeGetPcr()->NtTib.StackBase + 96),
             0,
             (__int64)&SkeThreadType,
             &v10,
             &v11);
  if ( (int)result >= 0 )
  {
    v7 = (__int64)v10;
    if ( v10 == StackBase )
    {
      SkobDereferenceObject((__int64)v10);
      goto LABEL_11;
    }
    SkiSetThreadExitStatus(v10, 0, a2);
    _InterlockedOr((volatile signed __int32 *)(v7 + 172), 2u);
    v9 = *(_QWORD *)(v7 + 64);
    if ( v9 )
    {
      memset_0(v12, v8, sizeof(v12));
      _interlockedbittestandset(
        &v12[(unsigned __int64)*(unsigned __int16 *)(v9 + 180) >> 5],
        *(_WORD *)(v9 + 180) & 0x1F);
      SkeGenericIpiCall(v12, 0, 0, 0);
    }
    SkobDereferenceObject(v7);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1400981f4  mov     [rsp+arg_8], rbx
0x1400981f9  mov     [rsp+arg_10], rsi
0x1400981fe  push    rdi
0x1400981ff  sub     rsp, 150h
0x140098206  mov     rax, cs:__security_cookie
0x14009820d  xor     rax, rsp
0x140098210  mov     [rsp+158h+var_18], rax
0x140098218  mov     esi, edx
0x14009821a  mov     rbx, rcx
0x14009821d  xor     edx, edx; Val
0x14009821f  lea     rcx, [rsp+158h+var_118]; void *
0x140098224  mov     r8d, 100h; Size
0x14009822a  call    memset_0
0x14009822f  mov     rdi, gs:8
0x140098238  mov     [rsp+158h+var_128], 0
0x140098241  test    rbx, rbx
0x140098244  jnz     short loc_140098263
0x140098246  mov     rax, [rdi+48h]
0x14009824a  mov     ecx, [rax+0BCh]
0x140098250  cmp     ecx, 1
0x140098253  jnz     loc_140098332
0x140098259  mov     eax, 0C00000DBh
0x14009825e  jmp     loc_140098307
0x140098263  mov     rdx, gs:8
0x14009826c  lea     rax, [rsp+158h+var_120]
0x140098271  mov     [rsp+158h+var_130], rax
0x140098276  lea     r9, SkeThreadType
0x14009827d  lea     rax, [rsp+158h+var_128]
0x140098282  xor     r8d, r8d
0x140098285  mov     rcx, rbx
0x140098288  mov     [rsp+158h+var_138], rax
0x14009828d  mov     dl, [rdx+60h]
0x140098290  call    SkobReferenceObjectByHandle
0x140098295  test    eax, eax
0x140098297  js      short loc_140098307
0x140098299  mov     rbx, [rsp+158h+var_128]
0x14009829e  mov     rcx, rbx
0x1400982a1  cmp     rbx, rdi
0x1400982a4  jz      loc_14009832D
0x1400982aa  mov     r8d, esi
0x1400982ad  xor     edx, edx
0x1400982af  call    SkiSetThreadExitStatus
0x1400982b4  lock or dword ptr [rbx+0ACh], 2
0x1400982bc  mov     rdi, [rbx+40h]
0x1400982c0  test    rdi, rdi
0x1400982c3  jz      short loc_1400982FD
0x1400982c5  mov     r8d, 100h; Size
0x1400982cb  lea     rcx, [rsp+158h+var_118]; void *
0x1400982d0  call    memset_0
0x1400982d5  movzx   ecx, word ptr [rdi+0B4h]
0x1400982dc  xor     r9d, r9d
0x1400982df  mov     eax, ecx
0x1400982e1  xor     r8d, r8d
0x1400982e4  shr     rcx, 5
0x1400982e8  and     eax, 1Fh
0x1400982eb  xor     edx, edx
0x1400982ed  lock bts [rsp+rcx*4+158h+var_118], eax
0x1400982f3  lea     rcx, [rsp+158h+var_118]
0x1400982f8  call    SkeGenericIpiCall
0x1400982fd  mov     rcx, rbx
0x140098300  call    SkobDereferenceObject
0x140098305  xor     eax, eax
0x140098307  mov     rcx, [rsp+158h+var_18]
0x14009830f  xor     rcx, rsp; StackCookie
0x140098312  call    __security_check_cookie
0x140098317  lea     r11, [rsp+158h+var_8]
0x14009831f  mov     rbx, [r11+18h]
0x140098323  mov     rsi, [r11+20h]
0x140098327  mov     rsp, r11
0x14009832a  pop     rdi
0x14009832b  retn
0x14009832d  call    SkobDereferenceObject
0x140098332  mov     edx, esi
0x140098334  mov     cl, 1
0x140098336  call    SkiTerminateThread
```
