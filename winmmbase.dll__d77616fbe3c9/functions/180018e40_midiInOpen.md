# midiInOpen

- ea: `0x180018e40`
- end: `0x180018ff7`
- name: `midiInOpen`
- size: `439`
- prototype: `MMRESULT __stdcall(LPHMIDIIN phmi, UINT uDeviceID, DWORD_PTR dwCallback, DWORD_PTR dwInstance, DWORD fdwOpen)`
- caller_count: `0`
- callee_count: `9`
- tags: `installer_update`

## callees

- `0x180001b70`
- `0x1800065d0`
- `0x180007d70`
- `0x18000aef0`
- `0x18000e0d0`
- `0x18000e828`
- `0x1800106c0`
- `0x180018e40`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018f35`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018f35`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018f46`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018fa4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018f46`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018fa4`

## pseudocode

```c
MMRESULT __stdcall midiInOpen(
        LPHMIDIIN phmi,
        UINT uDeviceID,
        DWORD_PTR dwCallback,
        DWORD_PTR dwInstance,
        DWORD fdwOpen)
{
  MMRESULT result; // eax
  struct _MMDRV *v9; // rdi
  MMRESULT v10; // esi
  struct _RTL_CRITICAL_SECTION *v11; // rax
  struct _RTL_CRITICAL_SECTION *v12; // rbx
  DWORD_PTR v13; // rax
  LONG v14; // [rsp+30h] [rbp-50h] BYREF
  struct _MMDRV *v15; // [rsp+38h] [rbp-48h] BYREF
  DWORD_PTR v16; // [rsp+40h] [rbp-40h]
  _OWORD v17[3]; // [rsp+48h] [rbp-38h] BYREF

  v16 = dwInstance;
  v15 = 0;
  v14 = 0;
  memset(v17, 0, 44);
  if ( !phmi )
    return 11;
  if ( uDeviceID != -1 )
  {
    if ( (fdwOpen & 0x3FDA) == 0 )
      goto LABEL_4;
    return 10;
  }
  if ( (fdwOpen & 0xBFDA) != 0 )
    return 10;
LABEL_4:
  if ( dwCallback && !(unsigned int)ValidateCallbackType(dwCallback, HIWORD(fdwOpen)) )
    return 11;
  *phmi = 0;
  ClientUpdatePnpInfo();
  result = midiReferenceDriverById(&midiindrvZ, uDeviceID, &v15, &v14);
  if ( !result )
  {
    v9 = v15;
    if ( *((_QWORD *)v15 + 10) )
    {
      v11 = NewHandle(4, *((_QWORD *)v15 + 12), 0x30u);
      v12 = v11;
      if ( v11 )
      {
        EnterCriticalSection(v11 - 1);
        v12[-2].RecursionCount |= 2u;
        LeaveCriticalSection(&HandleListCritSec);
        v12->LockCount = v14;
        v13 = v16;
        v12->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)v9;
        LODWORD(v12->LockSemaphore) = uDeviceID;
        HIDWORD(v12->LockSemaphore) = 0;
        *(_QWORD *)&v17[1] = v13;
        *(_QWORD *)&v17[0] = v12;
        *((_QWORD *)&v17[0] + 1) = dwCallback;
        *((_QWORD *)&v17[1] + 1) = v12->DebugInfo[2].CriticalSection;
        v10 = (*((__int64 (__fastcall **)(_QWORD, __int64, HANDLE *, _OWORD *, _QWORD))v9 + 10))(
                (unsigned int)v12->LockCount,
                55,
                &v12->OwningThread,
                v17,
                fdwOpen);
        if ( !v10 )
          v12[-2].RecursionCount &= ~2u;
        LeaveCriticalSection(v12 - 1);
        if ( v10 )
        {
          FreeHandle((__int64)v12);
        }
        else
        {
          _InterlockedIncrement((volatile signed __int32 *)v9 + 23);
          *phmi = (HMIDIIN)v12;
        }
      }
      else
      {
        v10 = 7;
      }
    }
    else
    {
      v10 = 6;
    }
    mregDecUsagePtr(v9);
    return v10;
  }
  return result;
}

```

## disassembly

```asm
0x180018e40  mov     [rsp-38h+arg_8], rbx
0x180018e45  push    rbp
0x180018e46  push    rsi
0x180018e47  push    rdi
0x180018e48  push    r12
0x180018e4a  push    r13
0x180018e4c  push    r14
0x180018e4e  push    r15
0x180018e50  mov     rbp, rsp
0x180018e53  sub     rsp, 80h
0x180018e5a  mov     rax, cs:__security_cookie
0x180018e61  xor     rax, rsp
0x180018e64  mov     [rbp+var_8], rax
0x180018e68  xorps   xmm0, xmm0
0x180018e6b  mov     [rbp+var_40], r9
0x180018e6f  xor     r13d, r13d
0x180018e72  mov     r15, r8
0x180018e75  mov     [rbp+var_48], r13
0x180018e79  mov     r12d, edx
0x180018e7c  mov     [rbp+var_50], r13d
0x180018e80  mov     r14, rcx
0x180018e83  movups  xmmword ptr [rbp+var_28], xmm0
0x180018e87  movups  xmmword ptr [rbp+var_28+0Ch], xmm0
0x180018e8b  movups  [rbp+var_38], xmm0
0x180018e8f  test    rcx, rcx
0x180018e92  jz      loc_180018FCB
0x180018e98  mov     esi, [rbp+fdwOpen]
0x180018e9b  movzx   eax, si
0x180018e9e  cmp     edx, 0FFFFFFFFh
0x180018ea1  jnz     short loc_180018EFD
0x180018ea3  test    eax, 0FFFFBFDAh
0x180018ea8  jnz     short loc_180018F04
0x180018eaa  test    r15, r15
0x180018ead  jz      short loc_180018EC4
0x180018eaf  mov     edx, esi
0x180018eb1  mov     rcx, r15
0x180018eb4  shr     edx, 10h
0x180018eb7  call    ValidateCallbackType
0x180018ebc  test    eax, eax
0x180018ebe  jz      loc_180018FCB
0x180018ec4  mov     [r14], r13
0x180018ec7  call    ClientUpdatePnpInfo
0x180018ecc  lea     r9, [rbp+var_50]
0x180018ed0  mov     edx, r12d
0x180018ed3  lea     r8, [rbp+var_48]
0x180018ed7  lea     rcx, midiindrvZ
0x180018ede  call    midiReferenceDriverById
0x180018ee3  test    eax, eax
0x180018ee5  jnz     loc_180018FD0
0x180018eeb  mov     rdi, [rbp+var_48]
0x180018eef  cmp     [rdi+50h], r13
0x180018ef3  jnz     short loc_180018F0E
0x180018ef5  lea     esi, [rax+6]
0x180018ef8  jmp     loc_180018FBF
0x180018efd  test    eax, 0FFFF3FDAh
0x180018f02  jz      short loc_180018EAA
0x180018f04  mov     eax, 0Ah
0x180018f09  jmp     loc_180018FD0
0x180018f0e  mov     rdx, [rdi+60h]
0x180018f12  mov     r8d, 30h ; '0'
0x180018f18  lea     ecx, [r8-2Ch]
0x180018f1c  call    NewHandle
0x180018f21  mov     rbx, rax
0x180018f24  test    rax, rax
0x180018f27  jnz     short loc_180018F31
0x180018f29  lea     esi, [rax+7]
0x180018f2c  jmp     loc_180018FBF
0x180018f31  lea     rcx, [rax-28h]; lpCriticalSection
0x180018f35  call    cs:__imp_EnterCriticalSection
0x180018f3b  or      dword ptr [rbx-44h], 2
0x180018f3f  lea     rcx, HandleListCritSec; lpCriticalSection
0x180018f46  call    cs:__imp_LeaveCriticalSection
0x180018f4c  mov     eax, [rbp+var_50]
0x180018f4f  lea     r8, [rbx+10h]
0x180018f53  mov     [rbx+8], eax
0x180018f56  lea     r9, [rbp+var_38]
0x180018f5a  mov     rax, [rbp+var_40]
0x180018f5e  mov     edx, 37h ; '7'
0x180018f63  mov     [rbx], rdi
0x180018f66  mov     [rbx+18h], r12d
0x180018f6a  mov     [rbx+1Ch], r13d
0x180018f6e  mov     qword ptr [rbp+var_28], rax
0x180018f72  mov     qword ptr [rbp+var_38], rbx
0x180018f76  mov     qword ptr [rbp+var_38+8], r15
0x180018f7a  mov     rax, [rbx]
0x180018f7d  mov     [rsp+80h+var_60], rsi
0x180018f82  mov     rcx, [rax+68h]
0x180018f86  mov     qword ptr [rbp+var_28+8], rcx
0x180018f8a  mov     ecx, [rbx+8]
0x180018f8d  mov     rax, [rdi+50h]
0x180018f91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018f96  mov     esi, eax
0x180018f98  test    eax, eax
0x180018f9a  jnz     short loc_180018FA0
0x180018f9c  and     dword ptr [rbx-44h], 0FFFFFFFDh
0x180018fa0  lea     rcx, [rbx-28h]; lpCriticalSection
0x180018fa4  call    cs:__imp_LeaveCriticalSection
0x180018faa  test    esi, esi
0x180018fac  jz      short loc_180018FB8
0x180018fae  mov     rcx, rbx
0x180018fb1  call    FreeHandle
0x180018fb6  jmp     short loc_180018FBF
0x180018fb8  lock inc dword ptr [rdi+5Ch]
0x180018fbc  mov     [r14], rbx
0x180018fbf  mov     rcx, rdi; struct _MMDRV *
0x180018fc2  call    mregDecUsagePtr
0x180018fc7  mov     eax, esi
0x180018fc9  jmp     short loc_180018FD0
0x180018fcb  mov     eax, 0Bh
0x180018fd0  mov     rcx, [rbp+var_8]
0x180018fd4  xor     rcx, rsp; StackCookie
0x180018fd7  call    __security_check_cookie
0x180018fdc  mov     rbx, [rsp+80h+arg_8]
0x180018fe4  add     rsp, 80h
0x180018feb  pop     r15
0x180018fed  pop     r14
0x180018fef  pop     r13
0x180018ff1  pop     r12
0x180018ff3  pop     rdi
0x180018ff4  pop     rsi
0x180018ff5  pop     rbp
0x180018ff6  retn
```
