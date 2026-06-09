# CLog::DoSearch(int,long,CObjId const &,ulong *,CDomainRelativeObjId *,CMachineId *,CDomainRelativeObjId *)

- ea: `0x180006bf0`
- end: `0x180007398`
- name: `?DoSearch@CLog@@AEAAHHJAEBUCObjId@@PEAKPEAUCDomainRelativeObjId@@PEAUCMachineId@@2@Z`
- size: `1960`
- prototype: `__int64 __fastcall(CLog *this, __int64, __int64, const struct CObjId *, unsigned int *, struct CDomainRelativeObjId *, struct CMachineId *, union _LARGE_INTEGER *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callers

- `0x180006a80`

## callees

- `0x1800028f0`
- `0x180006bf0`
- `0x180007cb0`
- `0x180008430`
- `0x18000d038`

## import_xrefs

- `ntdll!NtWriteFile` at `0x180006f22`
- `ntdll!NtWriteFile` at `0x1800071ef`
- `ntdll!NtWriteFile` at `0x180006f22`
- `ntdll!NtWriteFile` at `0x1800071ef`
- `ntdll!NtWaitForSingleObject` at `0x180006ddd`
- `ntdll!NtWaitForSingleObject` at `0x180006f71`
- `ntdll!NtWaitForSingleObject` at `0x1800070db`
- `ntdll!NtWaitForSingleObject` at `0x18000723c`
- `ntdll!NtWaitForSingleObject` at `0x180006ddd`
- `ntdll!NtWaitForSingleObject` at `0x180006f71`
- `ntdll!NtWaitForSingleObject` at `0x1800070db`
- `ntdll!NtWaitForSingleObject` at `0x18000723c`
- `ntdll!NtReadFile` at `0x180006dc4`
- `ntdll!NtReadFile` at `0x1800070c2`
- `ntdll!NtReadFile` at `0x180006dc4`
- `ntdll!NtReadFile` at `0x1800070c2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006e2b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007128`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006e2b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007128`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006e65`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000715c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006e65`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000715c`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180006e11`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000710e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180006e11`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000710e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180006d4c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180006f89`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180007250`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000731f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000733a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000734e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180007362`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000737d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180007391`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180006d4c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180006f89`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180007250`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000731f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000733a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000734e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180007362`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000737d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180007391`

## pseudocode

```c
__int64 __fastcall CLog::DoSearch(
        CLog *this,
        __int64 a2,
        __int64 a3,
        const struct CObjId *a4,
        unsigned int *a5,
        struct CDomainRelativeObjId *a6,
        struct CMachineId *a7,
        union _LARGE_INTEGER *a8)
{
  unsigned int v8; // r15d
  unsigned int v9; // r11d
  int v10; // r10d
  unsigned int v11; // ebx
  int v12; // r8d
  unsigned int v13; // r14d
  __int64 v14; // r11
  bool v15; // zf
  int v16; // edi
  __int64 v17; // rsi
  __int64 v18; // rax
  __int64 v19; // r14
  __int64 v20; // rcx
  __int64 v21; // r12
  __int64 v22; // rdx
  LONGLONG v23; // r13
  union _LARGE_INTEGER v24; // r8
  union _LARGE_INTEGER v25; // r9
  __int64 v26; // r10
  ULONG Length; // ecx
  int v28; // r14d
  NTSTATUS v29; // eax
  struct CTrkWksSvc *v30; // r13
  __int16 v31; // di
  __int64 v32; // rdx
  __int64 v33; // rax
  ULONG v35; // r8d
  union _LARGE_INTEGER v36; // rax
  signed int v37; // eax
  __int64 v38; // rsi
  void *Buffer; // r9
  void *v40; // r10
  void *v41; // r9
  void *v42; // r10
  int v43; // r8d
  unsigned int v44; // r12d
  unsigned int v45; // ecx
  int v46; // eax
  int i; // r14d
  ULONG v48; // ecx
  int v49; // r12d
  NTSTATUS v50; // eax
  struct CTrkWksSvc *v51; // rdi
  __int16 v52; // si
  __int64 v53; // rdx
  __int64 v54; // rax
  ULONG v55; // r8d
  union _LARGE_INTEGER v56; // rax
  signed int Status; // eax
  __int64 v58; // r13
  union _LARGE_INTEGER v59; // rax
  union _LARGE_INTEGER v60; // [rsp+50h] [rbp-B0h] BYREF
  int v61; // [rsp+58h] [rbp-A8h]
  unsigned int v62; // [rsp+5Ch] [rbp-A4h]
  union _LARGE_INTEGER ByteOffset; // [rsp+60h] [rbp-A0h] BYREF
  LARGE_INTEGER v64; // [rsp+68h] [rbp-98h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+70h] [rbp-90h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+78h] [rbp-88h] BYREF
  struct _IO_STATUS_BLOCK v67; // [rsp+88h] [rbp-78h] BYREF
  CLog *v68; // [rsp+170h] [rbp+70h]
  int v69; // [rsp+178h] [rbp+78h]
  unsigned int v70; // [rsp+180h] [rbp+80h]

  v68 = this;
  v8 = *((_DWORD *)this + 6);
  v9 = 0;
  v70 = 0;
  if ( v8 != *((_DWORD *)this + 4) )
  {
    v10 = 0;
    v69 = 1;
    v11 = *(_DWORD *)(*((_QWORD *)this + 1) + 72LL);
    v62 = v11;
    while ( !v9 && v8 != *((_DWORD *)this + 4) )
    {
      v61 = v10 + 1;
      if ( v10 + 1 > v11 )
        goto LABEL_15;
      v58 = *((_QWORD *)this + 1);
      for ( i = -1; i; i += v46 )
      {
        if ( i > 0 )
        {
          v45 = *(_DWORD *)CLogFileSector::ReadLogEntry((CLogFileSector *)(v58 + 120), v8);
          v46 = -1;
        }
        else
        {
          v41 = *(void **)(v58 + 152);
          if ( !v41 )
            goto LABEL_41;
          v42 = *(void **)(v58 + 128);
          if ( !v42 )
            goto LABEL_41;
          v43 = *(_DWORD *)(v58 + 120);
          ByteOffset.QuadPart = 0;
          if ( (v43 & 1) == 0 || (v44 = *(_DWORD *)(v58 + 148), v8 < v44) || v8 >= v44 + *(_DWORD *)(v58 + 144) )
          {
            v67 = 0;
            if ( (v43 & 1) != 0 && (v43 & 2) != 0 )
            {
              v55 = *(_DWORD *)(v58 + 140);
              v56.QuadPart = v55 * (*(_DWORD *)(v58 + 136) + *(_DWORD *)(v58 + 148) / *(_DWORD *)(v58 + 144));
              IoStatusBlock = 0;
              v60 = v56;
              Status = NtWriteFile(v42, 0, 0, 0, &IoStatusBlock, v41, v55, &v60, 0);
              if ( Status == 259 )
              {
                Status = NtWaitForSingleObject(*(HANDLE *)(v58 + 128), 0, 0);
                if ( Status < 0 )
                {
LABEL_69:
                  RaiseException(Status, 0, 0, 0);
                  __debugbreak();
                }
                Status = IoStatusBlock.Status;
              }
              if ( Status < 0 )
                goto LABEL_69;
              if ( *(_DWORD *)(v58 + 140) != IoStatusBlock.Information )
              {
                RaiseException(0x8DEAD001, 0, 0, 0);
                __debugbreak();
              }
              if ( g_ptrkwks )
                CEntropyRecorder::Put((struct CTrkWksSvc *)((char *)g_ptrkwks + 48));
              CLogFileSector::RaiseIfNotOpen((CLogFileSector *)(v58 + 120));
              *(_DWORD *)(v58 + 120) &= ~2u;
            }
            v48 = *(_DWORD *)(v58 + 140);
            v49 = v8 / *(_DWORD *)(v58 + 144) + *(_DWORD *)(v58 + 136);
            ByteOffset.QuadPart = v48 * v49;
            v50 = NtReadFile(*(HANDLE *)(v58 + 128), 0, 0, 0, &v67, *(PVOID *)(v58 + 152), v48, &ByteOffset, 0);
            if ( v50 == 259 )
            {
              v50 = NtWaitForSingleObject(*(HANDLE *)(v58 + 128), 0, 0);
              if ( v50 < 0 )
                goto LABEL_80;
              v50 = v67.Status;
            }
            if ( v50 < 0 )
            {
LABEL_80:
              if ( v50 == -1073741202 )
              {
                RaiseException(0xC000026E, 0, 0, 0);
                __debugbreak();
              }
LABEL_82:
              RaiseException(0x8DEAD001, 0, 0, 0);
              __debugbreak();
            }
            v51 = g_ptrkwks;
            if ( g_ptrkwks )
            {
              v64.QuadPart = 0;
              QueryPerformanceCounter(&v64);
              v52 = LOWORD(v64.LowPart) ^ WORD2(v64.QuadPart) ^ ((v64.LowPart ^ v64.HighPart) >> 16);
              EnterCriticalSection((LPCRITICAL_SECTION)((char *)v51 + 56));
              v53 = (unsigned __int8)*((_DWORD *)v51 + 24);
              *((_BYTE *)v51 + v53 + 104) ^= HIBYTE(v52);
              ++*((_DWORD *)v51 + 25);
              *((_DWORD *)v51 + 24) = v53 + 1;
              v54 = (unsigned __int8)(v53 + 1);
              *((_BYTE *)v51 + v54 + 104) ^= v52;
              ++*((_DWORD *)v51 + 25);
              *((_DWORD *)v51 + 24) = v54 + 1;
              LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v51 + 56));
            }
            if ( *(_DWORD *)(v58 + 140) != v67.Information )
              goto LABEL_82;
            v44 = *(_DWORD *)(v58 + 144) * (v49 - *(_DWORD *)(v58 + 136));
            *(_DWORD *)(v58 + 120) |= 1u;
            *(_DWORD *)(v58 + 148) = v44;
          }
          v45 = *(_DWORD *)(124LL * (v8 - v44) + *(_QWORD *)(v58 + 152) + 4);
          v46 = 1;
        }
        if ( v45 >= *(_DWORD *)(v58 + 72) || v45 == v8 )
          goto LABEL_15;
        v8 = v45;
      }
      v38 = *((_QWORD *)v68 + 1);
      Buffer = *(void **)(v38 + 152);
      if ( !Buffer || (v40 = *(void **)(v38 + 128)) == 0 )
LABEL_41:
        TrkRaiseWin32Error(110);
      v12 = *(_DWORD *)(v38 + 120);
      ByteOffset.QuadPart = 0;
      if ( (v12 & 1) == 0 || (v13 = *(_DWORD *)(v38 + 148), v8 < v13) || v8 >= v13 + *(_DWORD *)(v38 + 144) )
      {
        IoStatusBlock = 0;
        if ( (v12 & 1) != 0 && (v12 & 2) != 0 )
        {
          v35 = *(_DWORD *)(v38 + 140);
          v36.QuadPart = v35 * (*(_DWORD *)(v38 + 136) + *(_DWORD *)(v38 + 148) / *(_DWORD *)(v38 + 144));
          v67 = 0;
          v60 = v36;
          v37 = NtWriteFile(v40, 0, 0, 0, &v67, Buffer, v35, &v60, 0);
          if ( v37 == 259 )
          {
            v37 = NtWaitForSingleObject(*(HANDLE *)(v38 + 128), 0, 0);
            if ( v37 < 0 )
            {
LABEL_37:
              RaiseException(v37, 0, 0, 0);
              __debugbreak();
            }
            v37 = v67.Status;
          }
          if ( v37 < 0 )
            goto LABEL_37;
          if ( *(_DWORD *)(v38 + 140) != v67.Information )
          {
            RaiseException(0x8DEAD001, 0, 0, 0);
            __debugbreak();
          }
          if ( g_ptrkwks )
            CEntropyRecorder::Put((struct CTrkWksSvc *)((char *)g_ptrkwks + 48));
          CLogFileSector::RaiseIfNotOpen((CLogFileSector *)(v38 + 120));
          *(_DWORD *)(v38 + 120) &= ~2u;
        }
        Length = *(_DWORD *)(v38 + 140);
        v28 = v8 / *(_DWORD *)(v38 + 144) + *(_DWORD *)(v38 + 136);
        ByteOffset.QuadPart = Length * v28;
        v29 = NtReadFile(*(HANDLE *)(v38 + 128), 0, 0, 0, &IoStatusBlock, *(PVOID *)(v38 + 152), Length, &ByteOffset, 0);
        if ( v29 == 259 )
        {
          v29 = NtWaitForSingleObject(*(HANDLE *)(v38 + 128), 0, 0);
          if ( v29 < 0 )
            goto LABEL_84;
          v29 = IoStatusBlock.Status;
        }
        if ( v29 < 0 )
        {
LABEL_84:
          if ( v29 == -1073741202 )
          {
            RaiseException(0xC000026E, 0, 0, 0);
            __debugbreak();
          }
LABEL_86:
          RaiseException(0x8DEAD001, 0, 0, 0);
          JUMPOUT(0x180007397LL);
        }
        v30 = g_ptrkwks;
        if ( g_ptrkwks )
        {
          PerformanceCount.QuadPart = 0;
          QueryPerformanceCounter(&PerformanceCount);
          v31 = LOWORD(PerformanceCount.LowPart)
              ^ WORD2(PerformanceCount.QuadPart)
              ^ ((PerformanceCount.LowPart ^ PerformanceCount.HighPart) >> 16);
          EnterCriticalSection((LPCRITICAL_SECTION)((char *)v30 + 56));
          v32 = (unsigned __int8)*((_DWORD *)v30 + 24);
          *((_BYTE *)v30 + v32 + 104) ^= HIBYTE(v31);
          ++*((_DWORD *)v30 + 25);
          *((_DWORD *)v30 + 24) = v32 + 1;
          v33 = (unsigned __int8)(v32 + 1);
          *((_BYTE *)v30 + v33 + 104) ^= v31;
          ++*((_DWORD *)v30 + 25);
          *((_DWORD *)v30 + 24) = v33 + 1;
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v30 + 56));
        }
        if ( *(_DWORD *)(v38 + 140) != IoStatusBlock.Information )
          goto LABEL_86;
        v13 = *(_DWORD *)(v38 + 144) * (v28 - *(_DWORD *)(v38 + 136));
        *(_DWORD *)(v38 + 120) |= 1u;
        *(_DWORD *)(v38 + 148) = v13;
      }
      v14 = *(_QWORD *)(v38 + 152) + 124LL * (v8 - v13);
      v15 = *(_DWORD *)(v14 + 8) == 2;
      v16 = *(_DWORD *)(v14 + 12);
      v17 = *(_QWORD *)(v14 + 36);
      v18 = *(_QWORD *)(v14 + 44);
      v19 = *(_QWORD *)(v14 + 52);
      v20 = *(_QWORD *)(v14 + 60);
      v21 = *(_QWORD *)(v14 + 68);
      v22 = *(_QWORD *)(v14 + 76);
      v23 = *(_QWORD *)(v14 + 84);
      v24 = *(union _LARGE_INTEGER *)(v14 + 92);
      v60 = *(union _LARGE_INTEGER *)(v14 + 100);
      v25 = *(union _LARGE_INTEGER *)(v14 + 108);
      if ( !v15 )
        return v70;
      if ( !v69 )
      {
        v69 = 0;
        if ( v16 != -1 )
        {
LABEL_15:
          RaiseException(0x8DEAD001, 0, 0, 0);
          __debugbreak();
        }
      }
      v26 = *(_QWORD *)a4 - *(_QWORD *)(v14 + 20);
      if ( *(_QWORD *)a4 == *(_QWORD *)(v14 + 20) )
        v26 = *((_QWORD *)a4 + 1) - *(_QWORD *)(v14 + 28);
      v9 = v70;
      v15 = v26 == 0;
      v10 = v61;
      v11 = v62;
      if ( v15 )
      {
        if ( a5 )
          *a5 = v8;
        if ( a6 )
        {
          *((_QWORD *)a6 + 1) = v18;
          *(_QWORD *)a6 = v17;
          *((_QWORD *)a6 + 3) = v20;
          *((_QWORD *)a6 + 2) = v19;
          *(_QWORD *)a7 = v21;
          *((_QWORD *)a7 + 1) = v22;
          v59 = v60;
          a8->QuadPart = v23;
          a8[1] = v24;
          a8[2] = v59;
          a8[3] = v25;
        }
        v10 = v61;
        v9 = 1;
        v70 = 1;
      }
      this = v68;
    }
  }
  return v9;
}

```

## disassembly

```asm
0x180006bf0  mov     [rsp-8+arg_18], r9
0x180006bf5  mov     [rsp-8+arg_10], r8d
0x180006bfa  mov     [rsp-8+arg_8], edx
0x180006bfe  mov     [rsp-8+arg_0], rcx
0x180006c03  push    rbp
0x180006c04  push    rbx
0x180006c05  push    rsi
0x180006c06  push    rdi
0x180006c07  push    r12
0x180006c09  push    r13
0x180006c0b  push    r14
0x180006c0d  push    r15
0x180006c0f  lea     rbp, [rsp-28h]
0x180006c14  sub     rsp, 128h
0x180006c1b  mov     r15d, [rcx+18h]
0x180006c1f  xor     edi, edi
0x180006c21  mov     r11d, edi
0x180006c24  mov     [rbp+60h+arg_10], edi
0x180006c2a  cmp     r15d, [rcx+10h]
0x180006c2e  jz      loc_180006EA1
0x180006c34  mov     rax, [rcx+8]
0x180006c38  mov     r10d, edi
0x180006c3b  mov     [rbp+60h+arg_8], 1
0x180006c42  mov     ebx, [rax+48h]
0x180006c45  mov     [rsp+160h+var_104], ebx
0x180006c49  jmp     loc_180006D1B
0x180006c4e  mov     r8d, [rsi+78h]
0x180006c52  mov     edx, r8d
0x180006c55  shl     edx, 1Fh
0x180006c58  sar     edx, 1Fh
0x180006c5b  mov     qword ptr [rsp+160h+var_100], rdi
0x180006c60  test    edx, edx
0x180006c62  jz      loc_180006D53
0x180006c68  mov     r14d, [rsi+94h]
0x180006c6f  cmp     r15d, r14d
0x180006c72  jb      loc_180006D53
0x180006c78  mov     ecx, [rsi+90h]
0x180006c7e  add     ecx, r14d
0x180006c81  cmp     r15d, ecx
0x180006c84  jnb     loc_180006D53
0x180006c8a  mov     eax, r15d
0x180006c8d  sub     eax, r14d
0x180006c90  imul    r11, rax, 7Ch ; '|'
0x180006c94  add     r11, [rsi+98h]
0x180006c9b  cmp     dword ptr [r11+8], 2
0x180006ca0  mov     r9, [r11+64h]
0x180006ca4  mov     edi, [r11+0Ch]
0x180006ca8  mov     rsi, [r11+24h]
0x180006cac  mov     rax, [r11+2Ch]
0x180006cb0  mov     r14, [r11+34h]
0x180006cb4  mov     rcx, [r11+3Ch]
0x180006cb8  mov     r12, [r11+44h]
0x180006cbc  mov     rdx, [r11+4Ch]
0x180006cc0  mov     r13, [r11+54h]
0x180006cc4  mov     r8, [r11+5Ch]
0x180006cc8  mov     qword ptr [rsp+160h+var_110], r9
0x180006ccd  mov     r9, [r11+6Ch]
0x180006cd1  jnz     loc_180006E9A
0x180006cd7  cmp     [rbp+60h+arg_8], 0
0x180006cdb  jz      loc_180006EB8
0x180006ce1  mov     rbx, [rbp+60h+arg_18]
0x180006ce8  mov     r10, [rbx]
0x180006ceb  sub     r10, [r11+14h]
0x180006cef  jnz     short loc_180006CF9
0x180006cf1  mov     r10, [rbx+8]
0x180006cf5  sub     r10, [r11+1Ch]
0x180006cf9  mov     r11d, [rbp+60h+arg_10]
0x180006d00  test    r10, r10
0x180006d03  mov     r10d, [rsp+160h+var_108]
0x180006d08  mov     edi, 0
0x180006d0d  mov     ebx, [rsp+160h+var_104]
0x180006d11  jz      loc_1800072A8
0x180006d17  mov     rcx, [rbp+60h+arg_0]
0x180006d1b  test    r11d, r11d
0x180006d1e  jnz     loc_180006EA1
0x180006d24  cmp     r15d, [rcx+10h]
0x180006d28  jz      loc_180006EA1
0x180006d2e  inc     r10d
0x180006d31  mov     [rsp+160h+var_108], r10d
0x180006d36  cmp     r10d, ebx
0x180006d39  jbe     loc_180007257
0x180006d3f  xor     r9d, r9d; lpArguments
0x180006d42  xor     r8d, r8d; nNumberOfArguments
0x180006d45  xor     edx, edx; dwExceptionFlags
0x180006d47  mov     ecx, 8DEAD001h; dwExceptionCode
0x180006d4c  call    cs:__imp_RaiseException
0x180006d52  int     3; Trap to Debugger
0x180006d53  movups  xmmword ptr [rsp+160h+var_E8], xmm0
0x180006d58  test    edx, edx
0x180006d5a  jz      short loc_180006D66
0x180006d5c  test    r8b, 2
0x180006d60  jnz     loc_180006ECD
0x180006d66  mov     ecx, [rsi+8Ch]
0x180006d6c  xor     edx, edx
0x180006d6e  mov     r14d, [rsi+88h]
0x180006d75  mov     eax, r15d
0x180006d78  div     dword ptr [rsi+90h]
0x180006d7e  mov     [rsp+160h+Key], rdi; Key
0x180006d83  xor     r9d, r9d; ApcContext
0x180006d86  add     r14d, eax
0x180006d89  xor     r8d, r8d; ApcRoutine
0x180006d8c  mov     eax, r14d
0x180006d8f  xor     edx, edx; Event
0x180006d91  imul    eax, ecx
0x180006d94  mov     qword ptr [rsp+160h+var_100], rax
0x180006d99  lea     rax, [rsp+160h+var_100]
0x180006d9e  mov     [rsp+160h+ByteOffset], rax; ByteOffset
0x180006da3  mov     rax, [rsi+98h]
0x180006daa  mov     [rsp+160h+Length], ecx; Length
0x180006dae  mov     rcx, [rsi+80h]; FileHandle
0x180006db5  mov     [rsp+160h+Buffer], rax; Buffer
0x180006dba  lea     rax, [rsp+160h+var_E8]
0x180006dbf  mov     [rsp+160h+IoStatusBlock], rax; IoStatusBlock
0x180006dc4  call    cs:__imp_NtReadFile
0x180006dca  cmp     eax, 103h
0x180006dcf  jnz     short loc_180006DEF
0x180006dd1  mov     rcx, [rsi+80h]; Handle
0x180006dd8  xor     r8d, r8d; Timeout
0x180006ddb  xor     edx, edx; Alertable
0x180006ddd  call    cs:__imp_NtWaitForSingleObject
0x180006de3  test    eax, eax
0x180006de5  js      loc_180007369
0x180006deb  mov     eax, dword ptr [rsp+160h+var_E8]
0x180006def  test    eax, eax
0x180006df1  js      loc_180007369
0x180006df7  mov     r13, cs:?g_ptrkwks@@3PEAVCTrkWksSvc@@EA; CTrkWksSvc * g_ptrkwks
0x180006dfe  test    r13, r13
0x180006e01  jz      short loc_180006E6B
0x180006e03  lea     rcx, [rsp+160h+PerformanceCount]; lpPerformanceCount
0x180006e08  mov     qword ptr [rsp+160h+PerformanceCount], 0
0x180006e11  call    cs:__imp_QueryPerformanceCounter
0x180006e17  mov     eax, dword ptr [rsp+160h+PerformanceCount+4]
0x180006e1b  lea     rcx, [r13+38h]; lpCriticalSection
0x180006e1f  xor     eax, dword ptr [rsp+160h+PerformanceCount]
0x180006e23  mov     edi, eax
0x180006e25  shr     edi, 10h
0x180006e28  xor     di, ax
0x180006e2b  call    cs:__imp_EnterCriticalSection
0x180006e31  mov     eax, [r13+60h]
0x180006e35  lea     rcx, [r13+38h]; lpCriticalSection
0x180006e39  movzx   edx, al
0x180006e3c  movzx   eax, di
0x180006e3f  shr     ax, 8
0x180006e43  xor     [rdx+r13+68h], al
0x180006e48  lea     eax, [rdx+1]
0x180006e4b  inc     dword ptr [r13+64h]
0x180006e4f  mov     [r13+60h], eax
0x180006e53  movzx   eax, al
0x180006e56  xor     [rax+r13+68h], dil
0x180006e5b  inc     dword ptr [r13+64h]
0x180006e5f  inc     eax
0x180006e61  mov     [r13+60h], eax
0x180006e65  call    cs:__imp_LeaveCriticalSection
0x180006e6b  mov     eax, [rsi+8Ch]
0x180006e71  cmp     rax, [rbp+60h+var_E8.Information]
0x180006e75  jnz     loc_180007384
0x180006e7b  sub     r14d, [rsi+88h]
0x180006e82  imul    r14d, [rsi+90h]
0x180006e8a  or      dword ptr [rsi+78h], 1
0x180006e8e  mov     [rsi+94h], r14d
0x180006e95  jmp     loc_180006C8A
0x180006e9a  mov     r11d, [rbp+60h+arg_10]
0x180006ea1  mov     eax, r11d
0x180006ea4  add     rsp, 128h
0x180006eab  pop     r15
0x180006ead  pop     r14
0x180006eaf  pop     r13
0x180006eb1  pop     r12
0x180006eb3  pop     rdi
0x180006eb4  pop     rsi
0x180006eb5  pop     rbx
0x180006eb6  pop     rbp
0x180006eb7  retn
0x180006eb8  mov     [rbp+60h+arg_8], 0
0x180006ebf  cmp     edi, 0FFFFFFFFh
0x180006ec2  jz      loc_180006CE1
0x180006ec8  jmp     loc_180006D3F
0x180006ecd  mov     eax, [rsi+94h]
0x180006ed3  xor     edx, edx
0x180006ed5  div     dword ptr [rsi+90h]
0x180006edb  mov     r8d, [rsi+8Ch]
0x180006ee2  xor     edx, edx; Event
0x180006ee4  add     eax, [rsi+88h]
0x180006eea  mov     rcx, r10; FileHandle
0x180006eed  imul    eax, r8d
0x180006ef1  mov     [rsp+160h+Key], rdi; Key
0x180006ef6  movups  xmmword ptr [rbp+60h+var_D8], xmm0
0x180006efa  mov     qword ptr [rsp+160h+var_110], rax
0x180006eff  lea     rax, [rsp+160h+var_110]
0x180006f04  mov     [rsp+160h+ByteOffset], rax; ByteOffset
0x180006f09  lea     rax, [rbp+60h+var_D8]
0x180006f0d  mov     [rsp+160h+Length], r8d; Length
0x180006f12  xor     r8d, r8d; ApcRoutine
0x180006f15  mov     [rsp+160h+Buffer], r9; Buffer
0x180006f1a  xor     r9d, r9d; ApcContext
0x180006f1d  mov     [rsp+160h+IoStatusBlock], rax; IoStatusBlock
0x180006f22  call    cs:__imp_NtWriteFile
0x180006f28  cmp     eax, 103h
0x180006f2d  jz      short loc_180006F65
0x180006f2f  test    eax, eax
0x180006f31  js      short loc_180006F7F
0x180006f33  mov     eax, [rsi+8Ch]
0x180006f39  cmp     rax, [rbp+60h+var_D8.Information]
0x180006f3d  jnz     loc_180007355
0x180006f43  mov     rcx, cs:?g_ptrkwks@@3PEAVCTrkWksSvc@@EA; CTrkWksSvc * g_ptrkwks
0x180006f4a  test    rcx, rcx
0x180006f4d  jnz     loc_18000729A
0x180006f53  lea     rcx, [rsi+78h]; this
0x180006f57  call    ?RaiseIfNotOpen@CLogFileSector@@AEBAXXZ; CLogFileSector::RaiseIfNotOpen(void)
0x180006f5c  and     dword ptr [rsi+78h], 0FFFFFFFDh
0x180006f60  jmp     loc_180006D66
0x180006f65  mov     rcx, [rsi+80h]; Handle
0x180006f6c  xor     r8d, r8d; Timeout
0x180006f6f  xor     edx, edx; Alertable
0x180006f71  call    cs:__imp_NtWaitForSingleObject
0x180006f77  test    eax, eax
0x180006f79  jns     loc_180007292
0x180006f7f  xor     r9d, r9d; lpArguments
0x180006f82  xor     r8d, r8d; nNumberOfArguments
0x180006f85  xor     edx, edx; dwExceptionFlags
0x180006f87  mov     ecx, eax; dwExceptionCode
0x180006f89  call    cs:__imp_RaiseException
0x180006f8f  int     3; Trap to Debugger
0x180006f90  test    r14d, r14d
0x180006f93  jnz     short loc_180006FC7
0x180006f95  mov     rax, [rbp+60h+arg_0]
0x180006f99  xorps   xmm0, xmm0
0x180006f9c  mov     rsi, [rax+8]
0x180006fa0  mov     r9, [rsi+98h]
0x180006fa7  test    r9, r9
0x180006faa  jz      short loc_180006FBC
0x180006fac  mov     r10, [rsi+80h]
0x180006fb3  test    r10, r10
0x180006fb6  jnz     loc_180006C4E
0x180006fbc  mov     ecx, 6Eh ; 'n'; int
0x180006fc1  call    ?TrkRaiseWin32Error@@YAXJ@Z; TrkRaiseWin32Error(long)
0x180006fc7  jg      loc_180007266
0x180006fcd  mov     r9, [r13+98h]
0x180006fd4  test    r9, r9
0x180006fd7  jz      short loc_180006FBC
0x180006fd9  mov     r10, [r13+80h]
0x180006fe0  test    r10, r10
0x180006fe3  jz      short loc_180006FBC
0x180006fe5  mov     r8d, [r13+78h]
0x180006fe9  mov     edx, r8d
0x180006fec  shl     edx, 1Fh
0x180006fef  sar     edx, 1Fh
0x180006ff2  mov     qword ptr [rsp+160h+var_100], rdi
0x180006ff7  test    edx, edx
0x180006ff9  jz      short loc_18000704E
0x180006ffb  mov     r12d, [r13+94h]
0x180007002  cmp     r15d, r12d
0x180007005  jb      short loc_18000704E
0x180007007  mov     ecx, [r13+90h]
0x18000700e  add     ecx, r12d
0x180007011  cmp     r15d, ecx
0x180007014  jnb     short loc_18000704E
0x180007016  mov     eax, r15d
0x180007019  sub     eax, r12d
0x18000701c  imul    rcx, rax, 7Ch ; '|'
0x180007020  mov     rax, [r13+98h]
0x180007027  mov     ecx, [rcx+rax+4]
0x18000702b  mov     eax, 1
0x180007030  cmp     ecx, [r13+48h]
0x180007034  jnb     loc_180006D3F
0x18000703a  cmp     ecx, r15d
0x18000703d  jz      loc_180006D3F
0x180007043  mov     r15d, ecx
0x180007046  add     r14d, eax
0x180007049  jmp     loc_180006F90
0x18000704e  xorps   xmm0, xmm0
0x180007051  movups  xmmword ptr [rbp+60h+var_D8], xmm0
0x180007055  test    edx, edx
0x180007057  jz      short loc_180007063
0x180007059  test    r8b, 2
0x18000705d  jnz     loc_180007195
0x180007063  mov     ecx, [r13+8Ch]
0x18000706a  xor     edx, edx
0x18000706c  mov     r12d, [r13+88h]
0x180007073  mov     eax, r15d
0x180007076  div     dword ptr [r13+90h]
0x18000707d  mov     [rsp+160h+Key], rdi; Key
0x180007082  xor     r9d, r9d; ApcContext
0x180007085  add     r12d, eax
0x180007088  xor     r8d, r8d; ApcRoutine
0x18000708b  mov     eax, r12d
0x18000708e  xor     edx, edx; Event
0x180007090  imul    eax, ecx
0x180007093  mov     qword ptr [rsp+160h+var_100], rax
0x180007098  lea     rax, [rsp+160h+var_100]
0x18000709d  mov     [rsp+160h+ByteOffset], rax; ByteOffset
0x1800070a2  mov     rax, [r13+98h]
0x1800070a9  mov     [rsp+160h+Length], ecx; Length
0x1800070ad  mov     rcx, [r13+80h]; FileHandle
0x1800070b4  mov     [rsp+160h+Buffer], rax; Buffer
0x1800070b9  lea     rax, [rbp+60h+var_D8]
0x1800070bd  mov     [rsp+160h+IoStatusBlock], rax; IoStatusBlock
0x1800070c2  call    cs:__imp_NtReadFile
0x1800070c8  cmp     eax, 103h
0x1800070cd  jnz     short loc_1800070EC
  ... truncated ...
```
