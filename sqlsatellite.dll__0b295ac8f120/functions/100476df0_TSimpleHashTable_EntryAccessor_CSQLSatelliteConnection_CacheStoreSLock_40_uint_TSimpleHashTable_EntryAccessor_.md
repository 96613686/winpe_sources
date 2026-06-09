# TSimpleHashTable_EntryAccessor<CSQLSatelliteConnection,CacheStoreSLock,40,uint>::TSimpleHashTable_EntryAccessor<CSQLSatelliteConnection,CacheStoreSLock,40,uint>(TSimpleHashTable<CSQLSatelliteConnection,CacheStoreSLock,40,uint> *,uint const &,unsigned __int64,uint)

- ea: `0x100476df0`
- end: `0x100476f74`
- name: `??0?$TSimpleHashTable_EntryAccessor@VCSQLSatelliteConnection@@UCacheStoreSLock@@$0CI@I@@QEAA@PEAV?$TSimpleHashTable@VCSQLSatelliteConnection@@UCacheStoreSLock@@$0CI@I@@AEBI_KI@Z`
- size: `388`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1004748a0`
- `0x100475aa0`
- `0x100476390`
- `0x100476740`

## callees

- `0x100476df0`
- `0x100477870`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x100476ecc`
- `KERNEL32!QueryPerformanceCounter` at `0x100476efc`
- `KERNEL32!QueryPerformanceCounter` at `0x100476ecc`
- `KERNEL32!QueryPerformanceCounter` at `0x100476efc`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100476eb7`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100476eec`
- `sqldk!SystemThread_TlsIndex` at `0x100476e7d`
- `sqldk!SystemThread_TlsOffset` at `0x100476e8e`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x100476e5c`

## pseudocode

```c
__int64 __fastcall TSimpleHashTable_EntryAccessor<CSQLSatelliteConnection,CacheStoreSLock,40,unsigned int>::TSimpleHashTable_EntryAccessor<CSQLSatelliteConnection,CacheStoreSLock,40,unsigned int>(
        __int64 a1,
        __int64 a2,
        _DWORD *a3,
        __int64 a4,
        int a5)
{
  unsigned __int64 v6; // r11
  volatile signed __int64 *v7; // r14
  LONGLONG v8; // rbx
  signed __int64 UniqueThread_low; // r15
  __int64 v10; // rbp
  __int64 v11; // r8
  LARGE_INTEGER v12; // rdi
  LARGE_INTEGER v13; // rax
  LONGLONG v14; // rcx
  bool v15; // cf
  __int64 result; // rax
  LARGE_INTEGER PerformanceCount; // [rsp+50h] [rbp+8h] BYREF
  LARGE_INTEGER v18; // [rsp+58h] [rbp+10h] BYREF

  v6 = *(_QWORD *)(a2 + 32) + ((unsigned __int64)(unsigned int)(*a3 % *(_DWORD *)(a2 + 40)) << 6);
  *(_QWORD *)a1 = v6;
  v7 = (volatile signed __int64 *)(v6 + 24);
  *(_DWORD *)(a1 + 8) = *a3;
  v8 = 0;
  *(_QWORD *)(a1 + 16) = *(_QWORD *)(a2 + 48);
  *(_DWORD *)(a1 + 32) = a5;
  *(_QWORD *)(a1 + 24) = a4;
  UniqueThread_low = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
  if ( !*(_DWORD *)(v6 + 24) && !_InterlockedCompareExchange64(v7, UniqueThread_low, 0) )
    return a1;
  if ( (SOS_PublicGlobals::sm_osStats & 0x84) != 0x84 )
  {
    Spinlock<22,1,268435713>::SpinToAcquireWithExponentialBackoff(v6 + 24, UniqueThread_low);
    return a1;
  }
  v10 = 0;
  v11 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  if ( v11 && *(_QWORD *)(v11 + 272) == v11 )
    v10 = *(_QWORD *)(v11 + 256);
  if ( v10 )
  {
    if ( Base_PublicGlobals::sm_invariantTscAvailable )
    {
      QueryPerformanceCounter(&PerformanceCount);
      v12 = PerformanceCount;
    }
    else
    {
      v12.QuadPart = MEMORY[0x7FFE0008];
    }
    Spinlock<22,1,268435713>::SpinToAcquireWithExponentialBackoff(v7, UniqueThread_low);
    if ( Base_PublicGlobals::sm_invariantTscAvailable )
    {
      QueryPerformanceCounter(&v18);
      v13 = v18;
    }
    else
    {
      v13.QuadPart = MEMORY[0x7FFE0008];
    }
    v14 = v13.QuadPart - v12.QuadPart;
    v15 = v13.QuadPart < (unsigned __int64)v12.QuadPart;
    result = a1;
    if ( !v15 )
      v8 = v14;
    *(_QWORD *)(v10 + 3192) += v8;
  }
  else
  {
    Spinlock<22,1,268435713>::SpinToAcquireWithExponentialBackoff(v6 + 24, UniqueThread_low);
    return a1;
  }
  return result;
}

```

## disassembly

```asm
0x100476df0  push    rbx
0x100476df2  push    rsi
0x100476df3  push    r14
0x100476df5  push    r15
0x100476df7  sub     rsp, 28h
0x100476dfb  mov     eax, [r8]
0x100476dfe  mov     rbx, rdx
0x100476e01  xor     edx, edx
0x100476e03  mov     rsi, rcx
0x100476e06  div     dword ptr [rbx+28h]
0x100476e09  mov     r11d, edx
0x100476e0c  shl     r11, 6
0x100476e10  add     r11, [rbx+20h]
0x100476e14  mov     [rcx], r11
0x100476e17  lea     r14, [r11+18h]
0x100476e1b  mov     eax, [r8]
0x100476e1e  mov     [rcx+8], eax
0x100476e21  mov     rax, [rbx+30h]
0x100476e25  xor     ebx, ebx
0x100476e27  mov     [rcx+10h], rax
0x100476e2b  mov     eax, [rsp+48h+arg_20]
0x100476e2f  mov     [rcx+20h], eax
0x100476e32  mov     [rcx+18h], r9
0x100476e36  mov     eax, gs:48h
0x100476e3e  mov     r15d, eax
0x100476e41  mov     eax, [r14]
0x100476e44  test    eax, eax
0x100476e46  jnz     short loc_100476E5C
0x100476e48  xor     eax, eax
0x100476e4a  lock cmpxchg [r14], r15
0x100476e4f  mov     eax, ebx
0x100476e51  setz    al
0x100476e54  test    eax, eax
0x100476e56  jnz     loc_100476F66
0x100476e5c  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x100476e63  mov     ecx, [rax]
0x100476e65  and     ecx, 84h
0x100476e6b  cmp     cl, 84h
0x100476e6e  jnz     loc_100476F5B
0x100476e74  mov     rdx, gs:58h
0x100476e7d  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100476e84  mov     [rsp+48h+arg_18], rbp
0x100476e89  mov     rbp, rbx
0x100476e8c  mov     ecx, [rax]
0x100476e8e  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100476e95  mov     r8d, [rax]
0x100476e98  add     r8, [rdx+rcx*8]
0x100476e9c  jz      short loc_100476EAE
0x100476e9e  cmp     [r8+110h], r8
0x100476ea5  jnz     short loc_100476EAE
0x100476ea7  mov     rbp, [r8+100h]
0x100476eae  test    rbp, rbp
0x100476eb1  jz      loc_100476F3D
0x100476eb7  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x100476ebe  mov     [rsp+48h+var_28], rdi
0x100476ec3  cmp     [rax], ebx
0x100476ec5  jz      short loc_100476ED9
0x100476ec7  lea     rcx, [rsp+48h+PerformanceCount]; lpPerformanceCount
0x100476ecc  call    cs:__imp_QueryPerformanceCounter
0x100476ed2  mov     rdi, qword ptr [rsp+48h+PerformanceCount]
0x100476ed7  jmp     short loc_100476EE1
0x100476ed9  mov     rdi, ds:7FFE0008h
0x100476ee1  mov     rdx, r15
0x100476ee4  mov     rcx, r14
0x100476ee7  call    ?SpinToAcquireWithExponentialBackoff@?$Spinlock@$0BG@$00$0BAAAABAB@@@AEAAX_K@Z; Spinlock<22,1,268435713>::SpinToAcquireWithExponentialBackoff(unsigned __int64)
0x100476eec  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x100476ef3  cmp     [rax], ebx
0x100476ef5  jz      short loc_100476F09
0x100476ef7  lea     rcx, [rsp+48h+arg_8]; lpPerformanceCount
0x100476efc  call    cs:__imp_QueryPerformanceCounter
0x100476f02  mov     rax, qword ptr [rsp+48h+arg_8]
0x100476f07  jmp     short loc_100476F11
0x100476f09  mov     rax, ds:7FFE0008h
0x100476f11  mov     rcx, rax
0x100476f14  sub     rcx, rdi
0x100476f17  cmp     rax, rdi
0x100476f1a  mov     rdi, [rsp+48h+var_28]
0x100476f1f  mov     rax, rsi
0x100476f22  cmovnb  rbx, rcx
0x100476f26  add     [rbp+0C78h], rbx
0x100476f2d  mov     rbp, [rsp+48h+arg_18]
0x100476f32  add     rsp, 28h
0x100476f36  pop     r15
0x100476f38  pop     r14
0x100476f3a  pop     rsi
0x100476f3b  pop     rbx
0x100476f3c  retn
0x100476f3d  mov     rdx, r15
0x100476f40  mov     rcx, r14
0x100476f43  call    ?SpinToAcquireWithExponentialBackoff@?$Spinlock@$0BG@$00$0BAAAABAB@@@AEAAX_K@Z; Spinlock<22,1,268435713>::SpinToAcquireWithExponentialBackoff(unsigned __int64)
0x100476f48  mov     rbp, [rsp+48h+arg_18]
0x100476f4d  mov     rax, rsi
0x100476f50  add     rsp, 28h
0x100476f54  pop     r15
0x100476f56  pop     r14
0x100476f58  pop     rsi
0x100476f59  pop     rbx
0x100476f5a  retn
0x100476f5b  mov     rdx, r15
0x100476f5e  mov     rcx, r14
0x100476f61  call    ?SpinToAcquireWithExponentialBackoff@?$Spinlock@$0BG@$00$0BAAAABAB@@@AEAAX_K@Z; Spinlock<22,1,268435713>::SpinToAcquireWithExponentialBackoff(unsigned __int64)
0x100476f66  mov     rax, rsi
0x100476f69  add     rsp, 28h
0x100476f6d  pop     r15
0x100476f6f  pop     r14
0x100476f71  pop     rsi
0x100476f72  pop     rbx
0x100476f73  retn
```
