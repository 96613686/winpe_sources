# CVolumeLocationCache::AddVolume(CVolumeId const &,CMachineId const &)

- ea: `0x18000c55c`
- end: `0x18000c631`
- name: `?AddVolume@CVolumeLocationCache@@QEAAXAEBUCVolumeId@@AEBUCMachineId@@@Z`
- size: `213`
- prototype: `void __fastcall(CVolumeLocationCache *__hidden this, const struct CVolumeId *, const struct CMachineId *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1800022d4`
- `0x180004ac0`

## callees

- `0x180008cb4`
- `0x18000c55c`
- `0x18000daac`
- `0x180010fbe`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c59d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c59d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c61a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c61a`

## pseudocode

```c
void __fastcall CVolumeLocationCache::AddVolume(
        CVolumeLocationCache *this,
        const struct CVolumeId *a2,
        const struct CMachineId *a3)
{
  unsigned __int64 v6; // rax
  int Volume; // eax
  char *v8; // rcx
  char *v9; // rdx
  int v10; // ebx
  int v11; // eax
  struct _FILETIME FileTime; // [rsp+20h] [rbp-38h] BYREF

  v6 = -*(_QWORD *)a2;
  if ( !*(_QWORD *)a2 )
    v6 = _mm_srli_si128((__m128i)0LL, 8).m128i_u64[0] - *((_QWORD *)a2 + 1);
  if ( v6 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
    Volume = CVolumeLocationCache::_FindVolume(this, a2);
    v8 = (char *)this + 96;
    v9 = (char *)this + 56;
    if ( Volume == -1 )
    {
      v10 = *((_DWORD *)this + 12);
      v11 = v10 - 1;
      if ( v10 < 32 )
        v11 = *((_DWORD *)this + 12);
      memcpy_0(v8, v9, 40LL * v11);
      if ( v10 < 32 )
        ++*((_DWORD *)this + 12);
    }
    else
    {
      memcpy_0(v8, v9, 40LL * Volume);
    }
    *(_OWORD *)((char *)this + 56) = *(_OWORD *)a2;
    *(_OWORD *)((char *)this + 72) = *(_OWORD *)a3;
    CFILETIME::SetToUTC(&FileTime);
    *((struct _FILETIME *)this + 11) = FileTime;
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  }
}

```

## disassembly

```asm
0x18000c55c  mov     [rsp+arg_10], rbx
0x18000c561  push    rbp
0x18000c562  push    rsi
0x18000c563  push    rdi
0x18000c564  push    r14
0x18000c566  push    r15
0x18000c568  sub     rsp, 30h
0x18000c56c  xorps   xmm0, xmm0
0x18000c56f  mov     r15, r8
0x18000c572  movq    rax, xmm0
0x18000c577  mov     rbp, rdx
0x18000c57a  mov     rdi, rcx
0x18000c57d  sub     rax, [rdx]
0x18000c580  jnz     short loc_18000C590
0x18000c582  psrldq  xmm0, 8
0x18000c587  movq    rax, xmm0
0x18000c58c  sub     rax, [rdx+8]
0x18000c590  test    rax, rax
0x18000c593  jz      loc_18000C620
0x18000c599  add     rcx, 8; lpCriticalSection
0x18000c59d  call    cs:__imp_EnterCriticalSection
0x18000c5a3  mov     rdx, rbp; struct CVolumeId *
0x18000c5a6  mov     rcx, rdi; this
0x18000c5a9  call    ?_FindVolume@CVolumeLocationCache@@AEAAHAEBUCVolumeId@@@Z; CVolumeLocationCache::_FindVolume(CVolumeId const &)
0x18000c5ae  lea     rsi, [rdi+38h]
0x18000c5b2  lea     rcx, [rsi+28h]; void *
0x18000c5b6  mov     rdx, rsi; Src
0x18000c5b9  cmp     eax, 0FFFFFFFFh
0x18000c5bc  jnz     short loc_18000C5E3
0x18000c5be  mov     ebx, [rdi+30h]
0x18000c5c1  cmp     ebx, 20h ; ' '
0x18000c5c4  lea     eax, [rbx-1]
0x18000c5c7  cmovl   eax, ebx
0x18000c5ca  cdqe
0x18000c5cc  lea     r8, [rax+rax*4]
0x18000c5d0  shl     r8, 3; Size
0x18000c5d4  call    memcpy_0
0x18000c5d9  cmp     ebx, 20h ; ' '
0x18000c5dc  jge     short loc_18000C5F2
0x18000c5de  inc     dword ptr [rdi+30h]
0x18000c5e1  jmp     short loc_18000C5F2
0x18000c5e3  cdqe
0x18000c5e5  lea     r8, [rax+rax*4]
0x18000c5e9  shl     r8, 3; Size
0x18000c5ed  call    memcpy_0
0x18000c5f2  movups  xmm0, xmmword ptr [rbp+0]
0x18000c5f6  lea     rcx, [rsp+58h+FileTime]; lpFileTime
0x18000c5fb  movdqu  xmmword ptr [rsi], xmm0
0x18000c5ff  movups  xmm1, xmmword ptr [r15]
0x18000c603  movdqu  xmmword ptr [rdi+48h], xmm1
0x18000c608  call    ?SetToUTC@CFILETIME@@QEAAXXZ; CFILETIME::SetToUTC(void)
0x18000c60d  mov     rax, qword ptr [rsp+58h+FileTime.dwLowDateTime]
0x18000c612  lea     rcx, [rdi+8]; lpCriticalSection
0x18000c616  mov     [rdi+58h], rax
0x18000c61a  call    cs:__imp_LeaveCriticalSection
0x18000c620  mov     rbx, [rsp+58h+arg_10]
0x18000c625  add     rsp, 30h
0x18000c629  pop     r15
0x18000c62b  pop     r14
0x18000c62d  pop     rdi
0x18000c62e  pop     rsi
0x18000c62f  pop     rbp
0x18000c630  retn
```
