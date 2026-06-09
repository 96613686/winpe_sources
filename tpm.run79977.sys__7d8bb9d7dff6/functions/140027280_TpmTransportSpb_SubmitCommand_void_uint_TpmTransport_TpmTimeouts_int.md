# TpmTransportSpb::SubmitCommand(void *,uint,TpmTransport::TpmTimeouts *,int)

- ea: `0x140027280`
- end: `0x1400273f7`
- name: `?SubmitCommand@TpmTransportSpb@@UEAAJPEAXIPEAVTpmTimeouts@TpmTransport@@H@Z`
- size: `375`
- prototype: `__int64 __usercall@<rax>(TpmTransportSpb *__hidden this@<rcx>, void *@<rdx>, unsigned int@<r8d>, struct TpmTransport::TpmTimeouts *@<r9>, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1400078b8`
- `0x1400103f8`
- `0x140027280`
- `0x140039780`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x1400272c5`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400272c5`
- `ntoskrnl!KeReleaseMutex` at `0x1400273dd`
- `ntoskrnl!KeReleaseMutex` at `0x1400273dd`

## pseudocode

```c
__int64 __fastcall TpmTransportSpb::SubmitCommand(
        TpmTransportSpb *this,
        void *a2,
        unsigned int a3,
        struct TpmTransport::TpmTimeouts *a4,
        int a5)
{
  unsigned int v9; // ebx
  struct _KMUTANT *v10; // rbp
  __int64 v11; // rcx
  PDEVICE_OBJECT v12; // rcx
  __int64 v13; // rdx

  if ( a3 <= *((_DWORD *)this + 78) )
  {
    v10 = (struct _KMUTANT *)((char *)this + 128);
    KeWaitForSingleObject((char *)this + 128, Executive, 0, 0, 0);
    *((_DWORD *)this + 80) = a5;
    if ( TpmTransport::ShouldCancelCommand(this, a5 != 0) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 29, WPP_7dd49ddb627336f214b85aab2cfde8ce_Traceguids);
      v9 = -1073741536;
      goto LABEL_19;
    }
    v11 = *((_QWORD *)this + 42);
    if ( v11 )
    {
      v9 = (*(__int64 (__fastcall **)(__int64, void *, _QWORD))(*(_QWORD *)v11 + 8LL))(v11, a2, a3);
      if ( v9 != 258 )
      {
        *((_DWORD *)this + 79) = 1;
        *((_QWORD *)this + 41) = MEMORY[0xFFFFF78000000014] + 10000LL * *((unsigned int *)a4 + 4);
LABEL_19:
        KeReleaseMutex(v10, 0);
        return v9;
      }
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      {
LABEL_18:
        v9 = -1073741434;
        goto LABEL_19;
      }
      v13 = 31;
    }
    else
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_18;
      v13 = 30;
    }
    WPP_SF_(v12->AttachedDevice, v13, WPP_7dd49ddb627336f214b85aab2cfde8ce_Traceguids);
    goto LABEL_18;
  }
  return (unsigned int)-1073741811;
}

```

## disassembly

```asm
0x140027280  push    rbx
0x140027282  push    rbp
0x140027283  push    rsi
0x140027284  push    rdi
0x140027285  push    r14
0x140027287  sub     rsp, 30h
0x14002728b  mov     rsi, r9
0x14002728e  mov     ebx, r8d
0x140027291  mov     r14, rdx
0x140027294  mov     rdi, rcx
0x140027297  cmp     r8d, [rcx+138h]
0x14002729e  jbe     short loc_1400272AA
0x1400272a0  mov     ebx, 0C000000Dh
0x1400272a5  jmp     loc_1400273E9
0x1400272aa  lea     rbp, [rcx+80h]
0x1400272b1  mov     [rsp+58h+Timeout], 0; Timeout
0x1400272ba  mov     rcx, rbp; Object
0x1400272bd  xor     r9d, r9d; Alertable
0x1400272c0  xor     r8d, r8d; WaitMode
0x1400272c3  xor     edx, edx; WaitReason
0x1400272c5  call    cs:__imp_KeWaitForSingleObject
0x1400272cc  nop     dword ptr [rax+rax+00h]
0x1400272d1  mov     r9d, [rsp+58h+arg_20]
0x1400272d9  mov     rcx, rdi; this
0x1400272dc  test    r9d, r9d
0x1400272df  mov     [rdi+140h], r9d
0x1400272e6  setnz   dl; bool
0x1400272e9  call    ?ShouldCancelCommand@TpmTransport@@IEBA_N_N@Z; TpmTransport::ShouldCancelCommand(bool)
0x1400272ee  test    al, al
0x1400272f0  jz      short loc_14002732B
0x1400272f2  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400272f9  lea     rax, WPP_GLOBAL_Control
0x140027300  cmp     rcx, rax
0x140027303  jz      short loc_140027321
0x140027305  mov     eax, [rcx+2Ch]
0x140027308  test    al, 4
0x14002730a  jz      short loc_140027321
0x14002730c  mov     rcx, [rcx+18h]
0x140027310  lea     r8, WPP_7dd49ddb627336f214b85aab2cfde8ce_Traceguids
0x140027317  mov     edx, 1Dh
0x14002731c  call    WPP_SF_
0x140027321  mov     ebx, 0C0000120h
0x140027326  jmp     loc_1400273D8
0x14002732b  mov     rcx, [rdi+150h]
0x140027332  test    rcx, rcx
0x140027335  jnz     short loc_14002735C
0x140027337  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002733e  lea     rax, WPP_GLOBAL_Control
0x140027345  cmp     rcx, rax
0x140027348  jz      loc_1400273D3
0x14002734e  mov     eax, [rcx+2Ch]
0x140027351  test    al, 1
0x140027353  jz      short loc_1400273D3
0x140027355  mov     edx, 1Eh
0x14002735a  jmp     short loc_1400273C3
0x14002735c  mov     rax, [rcx]
0x14002735f  mov     r8d, ebx
0x140027362  mov     rdx, r14
0x140027365  mov     rax, [rax+8]
0x140027369  call    _guard_dispatch_icall
0x14002736e  mov     ebx, eax
0x140027370  cmp     eax, 102h
0x140027375  jz      short loc_1400273A4
0x140027377  mov     dword ptr [rdi+13Ch], 1
0x140027381  mov     rcx, 0FFFFF78000000014h
0x14002738b  mov     rcx, [rcx]
0x14002738e  mov     edx, [rsi+10h]
0x140027391  imul    r8, rdx, 2710h
0x140027398  add     r8, rcx
0x14002739b  mov     [rdi+148h], r8
0x1400273a2  jmp     short loc_1400273D8
0x1400273a4  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400273ab  lea     rax, WPP_GLOBAL_Control
0x1400273b2  cmp     rcx, rax
0x1400273b5  jz      short loc_1400273D3
0x1400273b7  mov     eax, [rcx+2Ch]
0x1400273ba  test    al, 1
0x1400273bc  jz      short loc_1400273D3
0x1400273be  mov     edx, 1Fh
0x1400273c3  mov     rcx, [rcx+18h]
0x1400273c7  lea     r8, WPP_7dd49ddb627336f214b85aab2cfde8ce_Traceguids
0x1400273ce  call    WPP_SF_
0x1400273d3  mov     ebx, 0C0000186h
0x1400273d8  xor     edx, edx; Wait
0x1400273da  mov     rcx, rbp; Mutex
0x1400273dd  call    cs:__imp_KeReleaseMutex
0x1400273e4  nop     dword ptr [rax+rax+00h]
0x1400273e9  mov     eax, ebx
0x1400273eb  add     rsp, 30h
0x1400273ef  pop     r14
0x1400273f1  pop     rdi
0x1400273f2  pop     rsi
0x1400273f3  pop     rbp
0x1400273f4  pop     rbx
0x1400273f5  retn
```
