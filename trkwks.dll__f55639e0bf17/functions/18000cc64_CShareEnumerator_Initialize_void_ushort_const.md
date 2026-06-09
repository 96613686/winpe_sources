# CShareEnumerator::Initialize(void *,ushort const *)

- ea: `0x18000cc64`
- end: `0x18000cd37`
- name: `?Initialize@CShareEnumerator@@QEAAXPEAXPEBG@Z`
- size: `211`
- prototype: `void __fastcall(CShareEnumerator *__hidden this, void *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000fa10`

## callees

- `0x18000b4a0`
- `0x18000cc64`
- `0x18000d038`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ccdc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ccdc`
- `KERNEL32!GetComputerNameW` at `0x18000ccd2`
- `KERNEL32!GetComputerNameW` at `0x18000ccd2`
- `srvcli!NetShareEnum` at `0x18000cd15`
- `srvcli!NetShareEnum` at `0x18000cd15`

## pseudocode

```c
void __fastcall CShareEnumerator::Initialize(CShareEnumerator *this, void *a2, const unsigned __int16 *a3)
{
  DWORD LastError; // eax
  signed int v5; // eax
  DWORD totalentries; // [rsp+50h] [rbp+8h] BYREF
  const unsigned __int16 *nSize; // [rsp+60h] [rbp+18h] BYREF

  nSize = a3;
  *((_QWORD *)this + 75) = a2;
  *((_DWORD *)this + 147) = -1;
  *((_DWORD *)this + 148) = 0;
  *((_DWORD *)this + 149) = 4096;
  *((_DWORD *)this + 12) = -1;
  *((_DWORD *)this + 10) = 1;
  totalentries = 0;
  StringCchCopyW((unsigned __int16 *)this + 32, 0x105u, L"\\\\");
  LODWORD(nSize) = 259;
  if ( !GetComputerNameW((LPWSTR)this + 34, (LPDWORD)&nSize) )
  {
    LastError = GetLastError();
    TrkRaiseWin32Error(LastError);
  }
  v5 = NetShareEnum(0, 0x1F6u, (LPBYTE *)this + 7, 0xFFFFFFFF, (LPDWORD)this + 11, &totalentries, 0);
  if ( v5 )
  {
    if ( v5 > 0 )
      v5 = (unsigned __int16)v5 | 0x80070000;
    TrkRaiseWin32Error(v5);
  }
}

```

## disassembly

```asm
0x18000cc64  mov     [rsp+nSize], r8
0x18000cc69  push    rbx
0x18000cc6a  sub     rsp, 40h
0x18000cc6e  mov     [rcx+258h], rdx
0x18000cc75  lea     r8, asc_180016D98; "\\\\"
0x18000cc7c  mov     rbx, rcx
0x18000cc7f  mov     dword ptr [rcx+24Ch], 0FFFFFFFFh
0x18000cc89  mov     dword ptr [rcx+250h], 0
0x18000cc93  mov     edx, 105h; unsigned __int64
0x18000cc98  mov     dword ptr [rcx+254h], 1000h
0x18000cca2  mov     dword ptr [rcx+30h], 0FFFFFFFFh
0x18000cca9  mov     dword ptr [rcx+28h], 1
0x18000ccb0  add     rcx, 40h ; '@'; unsigned __int16 *
0x18000ccb4  mov     [rsp+48h+arg_0], 0
0x18000ccbc  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000ccc1  lea     rcx, [rbx+44h]; lpBuffer
0x18000ccc5  mov     dword ptr [rsp+48h+nSize], 103h
0x18000cccd  lea     rdx, [rsp+48h+nSize]; nSize
0x18000ccd2  call    cs:__imp_GetComputerNameW
0x18000ccd8  test    eax, eax
0x18000ccda  jnz     short loc_18000CCEA
0x18000ccdc  call    cs:__imp_GetLastError
0x18000cce2  mov     ecx, eax; int
0x18000cce4  call    ?TrkRaiseWin32Error@@YAXJ@Z; TrkRaiseWin32Error(long)
0x18000ccea  lea     rcx, [rsp+48h+arg_0]
0x18000ccef  mov     [rsp+48h+resume_handle], 0; resume_handle
0x18000ccf8  mov     [rsp+48h+totalentries], rcx; totalentries
0x18000ccfd  lea     rax, [rbx+2Ch]
0x18000cd01  xor     ecx, ecx; servername
0x18000cd03  mov     [rsp+48h+entriesread], rax; entriesread
0x18000cd08  lea     r8, [rbx+38h]; bufptr
0x18000cd0c  or      r9d, 0FFFFFFFFh; prefmaxlen
0x18000cd10  mov     edx, 1F6h; level
0x18000cd15  call    cs:__imp_NetShareEnum
0x18000cd1b  test    eax, eax
0x18000cd1d  jz      short loc_18000CD31
0x18000cd1f  jle     short loc_18000CD29
0x18000cd21  movzx   eax, ax
0x18000cd24  or      eax, 80070000h
0x18000cd29  mov     ecx, eax; int
0x18000cd2b  call    ?TrkRaiseWin32Error@@YAXJ@Z; TrkRaiseWin32Error(long)
0x18000cd31  add     rsp, 40h
0x18000cd35  pop     rbx
0x18000cd36  retn
```
