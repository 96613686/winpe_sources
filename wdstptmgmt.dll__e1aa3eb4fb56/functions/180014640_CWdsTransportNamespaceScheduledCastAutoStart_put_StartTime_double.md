# CWdsTransportNamespaceScheduledCastAutoStart::put_StartTime(double)

- ea: `0x180014640`
- end: `0x180014704`
- name: `?put_StartTime@CWdsTransportNamespaceScheduledCastAutoStart@@UEAAJN@Z`
- size: `196`
- prototype: `__int64 __fastcall(CWdsTransportNamespaceScheduledCastAutoStart *__hidden this, double)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task`

## callees

- `0x180005e70`
- `0x180005ed0`
- `0x180014640`
- `0x18001470c`
- `0x18001e9f0`

## import_xrefs

- `OLEAUT32!__imp_VariantTimeToSystemTime` at `0x1800146a3`
- `OLEAUT32!__imp_VariantTimeToSystemTime` at `0x1800146a3`

## pseudocode

```c
__int64 __fastcall CWdsTransportNamespaceScheduledCastAutoStart::put_StartTime(
        CWdsTransportNamespaceScheduledCastAutoStart *this,
        DOUBLE a2)
{
  bool v3; // cf
  unsigned int v4; // ebx
  __int64 v5; // rdx
  __int64 v6; // r8
  int v7; // eax
  unsigned int v8; // eax
  _BYTE v10[16]; // [rsp+20h] [rbp-48h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+30h] [rbp-38h] BYREF

  CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(v10, (char *)this - 152);
  v3 = *((_DWORD *)this - 22) != 0;
  SystemTime = 0;
  v4 = v3 ? 0xC110010C : 0;
  if ( (int)ElValidateHr_8(v4, v5, v6, 530) >= 0 )
  {
    if ( VariantTimeToSystemTime(a2, &SystemTime) )
    {
      v7 = *((_DWORD *)this + 2);
      *((DOUBLE *)this + 2) = a2;
      if ( a2 < 1.0 )
        v8 = v7 & 0xFFFFFFFD;
      else
        v8 = v7 | 2;
      *((_DWORD *)this + 2) = v8;
    }
    else
    {
      v4 = -1055915763;
    }
  }
  CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(v10);
  return v4;
}

```

## disassembly

```asm
0x180014640  mov     [rsp+arg_10], rbx
0x180014645  push    rdi
0x180014646  sub     rsp, 60h
0x18001464a  movaps  [rsp+68h+var_18], xmm6
0x18001464f  mov     rax, cs:__security_cookie
0x180014656  xor     rax, rsp
0x180014659  mov     [rsp+68h+var_28], rax
0x18001465e  mov     rdi, rcx
0x180014661  lea     rdx, [rcx-98h]
0x180014668  lea     rcx, [rsp+68h+var_48]
0x18001466d  movaps  xmm6, xmm1
0x180014670  call    ??0?$CAutoTypeLock@VCCriticalSection@@@@QEAA@PEAVCCriticalSection@@H@Z; CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(CCriticalSection *,int)
0x180014675  mov     eax, [rdi-58h]
0x180014678  xorps   xmm0, xmm0
0x18001467b  neg     eax
0x18001467d  mov     r9d, 212h
0x180014683  movups  xmmword ptr [rsp+68h+SystemTime.wYear], xmm0
0x180014688  sbb     ebx, ebx
0x18001468a  and     ebx, 0C110010Ch
0x180014690  mov     ecx, ebx
0x180014692  call    ElValidateHr_8
0x180014697  test    eax, eax
0x180014699  js      short loc_1800146D7
0x18001469b  lea     rdx, [rsp+68h+SystemTime]; lpSystemTime
0x1800146a0  movaps  xmm0, xmm6; vtime
0x1800146a3  call    cs:__imp_VariantTimeToSystemTime
0x1800146aa  nop     dword ptr [rax+rax+00h]
0x1800146af  test    eax, eax
0x1800146b1  jnz     short loc_1800146BA
0x1800146b3  mov     ebx, 0C110010Dh
0x1800146b8  jmp     short loc_1800146D7
0x1800146ba  comisd  xmm6, cs:__real@3ff0000000000000
0x1800146c2  mov     eax, [rdi+8]
0x1800146c5  movsd   qword ptr [rdi+10h], xmm6
0x1800146ca  jb      short loc_1800146D1
0x1800146cc  or      eax, 2
0x1800146cf  jmp     short loc_1800146D4
0x1800146d1  and     eax, 0FFFFFFFDh
0x1800146d4  mov     [rdi+8], eax
0x1800146d7  lea     rcx, [rsp+68h+var_48]
0x1800146dc  call    ??1?$CAutoTypeLock@VCCriticalSection@@@@QEAA@XZ; CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(void)
0x1800146e1  mov     eax, ebx
0x1800146e3  mov     rcx, [rsp+68h+var_28]
0x1800146e8  xor     rcx, rsp; StackCookie
0x1800146eb  call    __security_check_cookie
0x1800146f0  mov     rbx, [rsp+68h+arg_10]
0x1800146f8  movaps  xmm6, [rsp+68h+var_18]
0x1800146fd  add     rsp, 60h
0x180014701  pop     rdi
0x180014702  retn
```
