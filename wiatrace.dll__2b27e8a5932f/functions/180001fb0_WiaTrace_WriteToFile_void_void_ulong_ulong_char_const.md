# WiaTrace::WriteToFile(void *,void *,ulong,ulong,char const *)

- ea: `0x180001fb0`
- end: `0x1800021c8`
- name: `?WriteToFile@WiaTrace@@YAJPEAX0KKPEBD@Z`
- size: `536`
- prototype: `__int64 __fastcall(HANDLE hFile, HANDLE hMutex, void *, unsigned int, struct _SYSTEMTIME *lpBuffer)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180001300`

## callees

- `0x180001010`
- `0x180001f20`
- `0x180001fb0`
- `0x180002300`
- `0x180002980`
- `0x1800031fa`

## import_xrefs

- `KERNEL32!SetFilePointerEx` at `0x180002037`
- `KERNEL32!SetFilePointerEx` at `0x180002053`
- `KERNEL32!SetFilePointerEx` at `0x180002037`
- `KERNEL32!SetFilePointerEx` at `0x180002053`
- `KERNEL32!ReleaseMutex` at `0x18000209a`
- `KERNEL32!ReleaseMutex` at `0x18000209a`
- `KERNEL32!WaitForSingleObject` at `0x18000200e`
- `KERNEL32!WaitForSingleObject` at `0x18000200e`
- `KERNEL32!WriteFile` at `0x180002091`
- `KERNEL32!WriteFile` at `0x18000213c`
- `KERNEL32!WriteFile` at `0x1800021b4`
- `KERNEL32!WriteFile` at `0x180002091`
- `KERNEL32!WriteFile` at `0x18000213c`
- `KERNEL32!WriteFile` at `0x1800021b4`

## string_xrefs

- `0x1800020de`: `WIA: ERROR!!! Failed to write to trace file, couldn't gain access!!!, WaitResult = %lu`

## pseudocode

```c
__int64 __fastcall WiaTrace::WriteToFile(
        HANDLE hFile,
        HANDLE hMutex,
        void *a3,
        unsigned int a4,
        struct _SYSTEMTIME *lpBuffer)
{
  __int16 v6; // r12
  DWORD v9; // ebx
  __int64 v10; // rbx
  struct _SYSTEMTIME *p_Buffer; // rdx
  void *v13; // rdx
  __int64 v14; // r8
  __int64 v15; // r8
  char *lpOverlapped; // [rsp+20h] [rbp-E0h]
  char *lpOverlappeda; // [rsp+20h] [rbp-E0h]
  unsigned int v18; // [rsp+28h] [rbp-D8h]
  DWORD NumberOfBytesWritten; // [rsp+30h] [rbp-D0h] BYREF
  LARGE_INTEGER v20; // [rsp+38h] [rbp-C8h] BYREF
  LARGE_INTEGER NewFilePointer; // [rsp+40h] [rbp-C0h] BYREF
  struct _SYSTEMTIME Buffer; // [rsp+50h] [rbp-B0h] BYREF

  v6 = (__int16)a3;
  NumberOfBytesWritten = 0;
  if ( !WiaTrace::g_TraceOutput_bMaxFileSizeReached )
  {
    v9 = WaitForSingleObject(hMutex, 0x2710u);
    if ( (v9 & 0xFFFFFF7F) != 0 )
    {
      memset_0(&Buffer, 0, 0x100u);
      StringCchPrintfA(
        (char *)&Buffer,
        0x100u,
        "WIA: ERROR!!! Failed to write to trace file, couldn't gain access!!!, WaitResult = %lu",
        v9);
      return 0;
    }
    NewFilePointer.QuadPart = 0;
    SetFilePointerEx(hFile, 0, &NewFilePointer, 2u);
    v20.QuadPart = 0;
    SetFilePointerEx(hFile, 0, &v20, 1u);
    if ( v20.QuadPart > (unsigned __int64)a4 )
    {
      memset_0(&Buffer, 0, 0x100u);
      if ( (v6 & 0x200) != 0 )
      {
        v10 = -1;
        WiaTrace::g_TraceOutput_bMaxFileSizeReached = 1;
        v14 = -1;
        do
          ++v14;
        while ( *((_BYTE *)&lpBuffer->wYear + v14) );
        WriteFile(hFile, lpBuffer, v14, &NumberOfBytesWritten, 0);
        WiaTrace::GetBanner((WiaTrace *)3, 0, 0, &Buffer, lpOverlappeda, v18);
        do
          ++v10;
        while ( *((_BYTE *)&Buffer.wYear + v10) );
        p_Buffer = &Buffer;
        goto LABEL_7;
      }
      WiaTrace::WrapFile(hFile, v13);
      WiaTrace::GetBanner((WiaTrace *)2, 0, 0, &Buffer, lpOverlapped, v18);
      v10 = -1;
      v15 = -1;
      do
        ++v15;
      while ( *((_BYTE *)&Buffer.wYear + v15) );
      WriteFile(hFile, &Buffer, v15, &NumberOfBytesWritten, 0);
      do
        ++v10;
      while ( *((_BYTE *)&lpBuffer->wYear + v10) );
    }
    else
    {
      v10 = -1;
      do
        ++v10;
      while ( *((_BYTE *)&lpBuffer->wYear + v10) );
    }
    p_Buffer = lpBuffer;
LABEL_7:
    WriteFile(hFile, p_Buffer, v10, &NumberOfBytesWritten, 0);
    ReleaseMutex(hMutex);
  }
  return 0;
}

```

## disassembly

```asm
0x180001fb0  push    rbp
0x180001fb2  push    rsi
0x180001fb3  push    rdi
0x180001fb4  push    r12
0x180001fb6  push    r13
0x180001fb8  push    r14
0x180001fba  push    r15
0x180001fbc  lea     rbp, [rsp-60h]
0x180001fc1  sub     rsp, 160h
0x180001fc8  mov     rax, cs:__security_cookie
0x180001fcf  xor     rax, rsp
0x180001fd2  mov     [rbp+90h+var_40], rax
0x180001fd6  mov     rdi, [rbp+90h+lpBuffer]
0x180001fdd  xor     r13d, r13d
0x180001fe0  cmp     cs:?g_TraceOutput_bMaxFileSizeReached@WiaTrace@@3HA, r13d; int WiaTrace::g_TraceOutput_bMaxFileSizeReached
0x180001fe7  mov     esi, r9d
0x180001fea  mov     r12d, r8d
0x180001fed  mov     [rsp+190h+NumberOfBytesWritten], r13d
0x180001ff2  mov     r14, rdx
0x180001ff5  mov     r15, rcx
0x180001ff8  jnz     loc_1800020A8
0x180001ffe  mov     edx, 2710h; dwMilliseconds
0x180002003  mov     [rsp+190h+arg_10], rbx
0x18000200b  mov     rcx, r14; hHandle
0x18000200e  call    cs:__imp_WaitForSingleObject
0x180002014  mov     ebx, eax
0x180002016  test    eax, 0FFFFFF7Fh
0x18000201b  jnz     loc_1800020C9
0x180002021  mov     r9d, 2; dwMoveMethod
0x180002027  mov     qword ptr [rsp+190h+NewFilePointer], r13
0x18000202c  lea     r8, [rsp+190h+NewFilePointer]; lpNewFilePointer
0x180002031  mov     edx, r13d; liDistanceToMove
0x180002034  mov     rcx, r15; hFile
0x180002037  call    cs:__imp_SetFilePointerEx
0x18000203d  mov     r9d, 1; dwMoveMethod
0x180002043  mov     qword ptr [rsp+190h+var_158], r13
0x180002048  lea     r8, [rsp+190h+var_158]; lpNewFilePointer
0x18000204d  mov     edx, r13d; liDistanceToMove
0x180002050  mov     rcx, r15; hFile
0x180002053  call    cs:__imp_SetFilePointerEx
0x180002059  cmp     dword ptr [rsp+190h+var_158+4], r13d
0x18000205e  jnz     loc_1800020F6
0x180002064  cmp     dword ptr [rsp+190h+var_158], esi
0x180002068  ja      loc_1800020F6
0x18000206e  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180002075  inc     rbx
0x180002078  cmp     [rdi+rbx], r13b
0x18000207c  jnz     short loc_180002075
0x18000207e  mov     rdx, rdi; lpBuffer
0x180002081  lea     r9, [rsp+190h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180002086  mov     [rsp+190h+lpOverlapped], r13; lpOverlapped
0x18000208b  mov     r8d, ebx; nNumberOfBytesToWrite
0x18000208e  mov     rcx, r15; hFile
0x180002091  call    cs:__imp_WriteFile
0x180002097  mov     rcx, r14; hMutex
0x18000209a  call    cs:__imp_ReleaseMutex
0x1800020a0  mov     rbx, [rsp+190h+arg_10]
0x1800020a8  xor     eax, eax
0x1800020aa  mov     rcx, [rbp+90h+var_40]
0x1800020ae  xor     rcx, rsp; StackCookie
0x1800020b1  call    __security_check_cookie
0x1800020b6  add     rsp, 160h
0x1800020bd  pop     r15
0x1800020bf  pop     r14
0x1800020c1  pop     r13
0x1800020c3  pop     r12
0x1800020c5  pop     rdi
0x1800020c6  pop     rsi
0x1800020c7  pop     rbp
0x1800020c8  retn
0x1800020c9  xor     edx, edx; Val
0x1800020cb  lea     rcx, [rsp+190h+Buffer]; void *
0x1800020d0  mov     r8d, 100h; Size
0x1800020d6  call    memset_0
0x1800020db  mov     r9d, ebx
0x1800020de  lea     r8, aWiaErrorFailed; "WIA: ERROR!!! Failed to write to trace "...
0x1800020e5  mov     edx, 100h; unsigned __int64
0x1800020ea  lea     rcx, [rsp+190h+Buffer]; char *
0x1800020ef  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800020f4  jmp     short loc_1800020A0
0x1800020f6  xor     edx, edx; Val
0x1800020f8  lea     rcx, [rsp+190h+Buffer]; void *
0x1800020fd  mov     r8d, 100h; Size
0x180002103  call    memset_0
0x180002108  bt      r12d, 9
0x18000210d  jnb     short loc_18000216E
0x18000210f  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180002116  mov     cs:?g_TraceOutput_bMaxFileSizeReached@WiaTrace@@3HA, 1; int WiaTrace::g_TraceOutput_bMaxFileSizeReached
0x180002120  mov     r8, rbx
0x180002123  inc     r8; nNumberOfBytesToWrite
0x180002126  cmp     [rdi+r8], r13b
0x18000212a  jnz     short loc_180002123
0x18000212c  lea     r9, [rsp+190h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180002131  mov     [rsp+190h+lpOverlapped], r13; char *
0x180002136  mov     rdx, rdi; lpBuffer
0x180002139  mov     rcx, r15; hFile
0x18000213c  call    cs:__imp_WriteFile
0x180002142  lea     r9, [rsp+190h+Buffer]; struct _SYSTEMTIME *
0x180002147  xor     r8d, r8d; char *
0x18000214a  xor     edx, edx; unsigned int
0x18000214c  mov     ecx, 3; this
0x180002151  call    ?GetBanner@WiaTrace@@YAJKPEBDPEAU_SYSTEMTIME@@PEADK@Z; WiaTrace::GetBanner(ulong,char const *,_SYSTEMTIME *,char *,ulong)
0x180002156  lea     rax, [rsp+190h+Buffer]
0x18000215b  inc     rbx
0x18000215e  cmp     [rax+rbx], r13b
0x180002162  jnz     short loc_18000215B
0x180002164  lea     rdx, [rsp+190h+Buffer]
0x180002169  jmp     loc_180002081
0x18000216e  mov     rcx, r15; hFile
0x180002171  call    ?WrapFile@WiaTrace@@YAJPEAX@Z; WiaTrace::WrapFile(void *)
0x180002176  lea     r9, [rsp+190h+Buffer]; struct _SYSTEMTIME *
0x18000217b  xor     r8d, r8d; char *
0x18000217e  xor     edx, edx; unsigned int
0x180002180  mov     ecx, 2; this
0x180002185  call    ?GetBanner@WiaTrace@@YAJKPEBDPEAU_SYSTEMTIME@@PEADK@Z; WiaTrace::GetBanner(ulong,char const *,_SYSTEMTIME *,char *,ulong)
0x18000218a  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180002191  lea     rax, [rsp+190h+Buffer]
0x180002196  mov     r8, rbx
0x180002199  inc     r8; nNumberOfBytesToWrite
0x18000219c  cmp     [rax+r8], r13b
0x1800021a0  jnz     short loc_180002199
0x1800021a2  lea     r9, [rsp+190h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800021a7  mov     [rsp+190h+lpOverlapped], r13; lpOverlapped
0x1800021ac  lea     rdx, [rsp+190h+Buffer]; lpBuffer
0x1800021b1  mov     rcx, r15; hFile
0x1800021b4  call    cs:__imp_WriteFile
0x1800021ba  inc     rbx
0x1800021bd  cmp     [rdi+rbx], r13b
0x1800021c1  jnz     short loc_1800021BA
0x1800021c3  jmp     loc_18000207E
```
