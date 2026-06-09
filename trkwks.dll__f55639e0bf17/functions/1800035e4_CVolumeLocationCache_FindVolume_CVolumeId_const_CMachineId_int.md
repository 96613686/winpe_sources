# CVolumeLocationCache::FindVolume(CVolumeId const &,CMachineId *,int *)

- ea: `0x1800035e4`
- end: `0x18000367d`
- name: `?FindVolume@CVolumeLocationCache@@QEAAHAEBUCVolumeId@@PEAUCMachineId@@PEAH@Z`
- size: `153`
- prototype: `_BOOL8 __fastcall(CVolumeLocationCache *this, const struct CVolumeId *, struct CMachineId *, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180004ac0`

## callees

- `0x1800035e4`
- `0x180008cb4`
- `0x18000daac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003606`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003606`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000365c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000365c`

## pseudocode

```c
_BOOL8 __fastcall CVolumeLocationCache::FindVolume(
        CVolumeLocationCache *this,
        const struct CVolumeId *a2,
        struct CMachineId *a3,
        int *a4)
{
  int Volume; // eax
  __int64 v9; // rbx
  struct _FILETIME v10; // rcx
  __int64 v11; // rcx
  BOOL v12; // eax
  struct _FILETIME FileTime; // [rsp+40h] [rbp+8h] BYREF

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  Volume = CVolumeLocationCache::_FindVolume(this, a2);
  v9 = Volume;
  if ( Volume != -1 )
  {
    CFILETIME::SetToUTC(&FileTime);
    v10 = FileTime;
    *(_OWORD *)a3 = *(_OWORD *)((char *)this + 40 * v9 + 72);
    v11 = *(_QWORD *)&v10 - *((_QWORD *)this + 5 * v9 + 11);
    v12 = *((_QWORD *)this + 167) == v11 || *((_QWORD *)this + 167) > v11;
    *a4 = v12;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  return (_DWORD)v9 != -1;
}

```

## disassembly

```asm
0x1800035e4  mov     [rsp+arg_8], rbx
0x1800035e9  mov     [rsp+arg_10], rbp
0x1800035ee  push    rsi
0x1800035ef  push    rdi
0x1800035f0  push    r14
0x1800035f2  sub     rsp, 20h
0x1800035f6  mov     rdi, rcx
0x1800035f9  mov     r14, r9
0x1800035fc  add     rcx, 8; lpCriticalSection
0x180003600  mov     rbp, r8
0x180003603  mov     rbx, rdx
0x180003606  call    cs:__imp_EnterCriticalSection
0x18000360c  mov     rdx, rbx; struct CVolumeId *
0x18000360f  mov     rcx, rdi; this
0x180003612  call    ?_FindVolume@CVolumeLocationCache@@AEAAHAEBUCVolumeId@@@Z; CVolumeLocationCache::_FindVolume(CVolumeId const &)
0x180003617  movsxd  rbx, eax
0x18000361a  cmp     ebx, 0FFFFFFFFh
0x18000361d  jz      short loc_180003658
0x18000361f  lea     rcx, [rsp+38h+FileTime]; lpFileTime
0x180003624  call    ?SetToUTC@CFILETIME@@QEAAXXZ; CFILETIME::SetToUTC(void)
0x180003629  mov     rcx, qword ptr [rsp+38h+FileTime.dwLowDateTime]
0x18000362e  lea     rdx, [rbx+rbx*4]
0x180003632  movups  xmm0, xmmword ptr [rdi+rdx*8+48h]
0x180003637  movdqu  xmmword ptr [rbp+0], xmm0
0x18000363c  sub     rcx, [rdi+rdx*8+58h]
0x180003641  cmp     [rdi+538h], rcx
0x180003648  jz      short loc_180003650
0x18000364a  jg      short loc_180003650
0x18000364c  xor     eax, eax
0x18000364e  jmp     short loc_180003655
0x180003650  mov     eax, 1
0x180003655  mov     [r14], eax
0x180003658  lea     rcx, [rdi+8]; lpCriticalSection
0x18000365c  call    cs:__imp_LeaveCriticalSection
0x180003662  mov     rbp, [rsp+38h+arg_10]
0x180003667  xor     eax, eax
0x180003669  cmp     ebx, 0FFFFFFFFh
0x18000366c  mov     rbx, [rsp+38h+arg_8]
0x180003671  setnz   al
0x180003674  add     rsp, 20h
0x180003678  pop     r14
0x18000367a  pop     rdi
0x18000367b  pop     rsi
0x18000367c  retn
```
