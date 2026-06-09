# CookupNodeId(uchar *,ushort)

- ea: `0x383ad3230`
- end: `0x383ad33db`
- name: `?CookupNodeId@@YAJPEAEG@Z`
- size: `427`
- prototype: `__int64 __fastcall(unsigned __int8 *, unsigned __int16)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x3838956d0`

## callees

- `0x3838434c0`
- `0x383ad3230`

## import_xrefs

- `KERNEL32!GetComputerNameW` at `0x383ad328c`
- `KERNEL32!GetComputerNameW` at `0x383ad328c`
- `KERNEL32!QueryPerformanceCounter` at `0x383ad32d9`
- `KERNEL32!QueryPerformanceCounter` at `0x383ad32d9`
- `KERNEL32!GlobalMemoryStatus` at `0x383ad331b`
- `KERNEL32!GlobalMemoryStatus` at `0x383ad331b`
- `KERNEL32!GetDiskFreeSpaceA` at `0x383ad3383`
- `KERNEL32!GetDiskFreeSpaceA` at `0x383ad3383`
- `ADVAPI32!AllocateLocallyUniqueId` at `0x383ad3351`
- `ADVAPI32!AllocateLocallyUniqueId` at `0x383ad3351`

## pseudocode

```c
__int64 __fastcall CookupNodeId(unsigned __int8 *a1)
{
  DWORD v2; // edx
  WCHAR *p_Buffer; // r8
  __int64 v4; // rax
  DWORD v5; // ecx
  DWORD nSize; // [rsp+30h] [rbp-39h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+38h] [rbp-31h] BYREF
  DWORD NumberOfFreeClusters; // [rsp+40h] [rbp-29h] BYREF
  DWORD SectorsPerCluster; // [rsp+44h] [rbp-25h] BYREF
  DWORD TotalNumberOfClusters; // [rsp+48h] [rbp-21h] BYREF
  DWORD BytesPerSector; // [rsp+4Ch] [rbp-1Dh] BYREF
  _MEMORYSTATUS v13; // [rsp+50h] [rbp-19h] BYREF
  _DWORD v14[2]; // [rsp+88h] [rbp+1Fh] BYREF
  WCHAR Buffer; // [rsp+90h] [rbp+27h] BYREF
  __int64 v16; // [rsp+92h] [rbp+29h]
  __int64 v17; // [rsp+9Ah] [rbp+31h]
  __int64 v18; // [rsp+A2h] [rbp+39h]
  int v19; // [rsp+AAh] [rbp+41h]
  __int16 v20; // [rsp+AEh] [rbp+45h]

  memset(v14, 0, 6);
  v16 = 0;
  Buffer = 0;
  v17 = 0;
  v18 = 0;
  v19 = 0;
  v20 = 0;
  nSize = 16;
  if ( GetComputerNameW(&Buffer, &nSize) )
  {
    v2 = 0;
    p_Buffer = &Buffer;
    nSize = 0;
    if ( Buffer )
    {
      do
      {
        v4 = v2++;
        *((_BYTE *)v14 + v4) ^= *((_BYTE *)++p_Buffer - 2);
        if ( v2 >= 6 )
          v2 = 0;
      }
      while ( *p_Buffer );
      nSize = v2;
    }
  }
  if ( QueryPerformanceCounter(&PerformanceCount) )
  {
    *(_DWORD *)((char *)v14 + 2) ^= PerformanceCount.HighPart ^ PerformanceCount.LowPart;
    v5 = PerformanceCount.HighPart ^ PerformanceCount.LowPart ^ v14[0];
  }
  else
  {
    v5 = v14[0];
  }
  v13.dwLength = 56;
  v14[0] = ((unsigned int)&v13.dwTotalPageFile + 1 + 31) ^ v5;
  *(_DWORD *)((char *)v14 + 2) ^= (unsigned int)v14;
  GlobalMemoryStatus(&v13);
  v14[0] ^= v13.dwMemoryLoad;
  *(_DWORD *)((char *)v14 + 2) ^= LODWORD(v13.dwTotalPhys);
  v14[0] ^= LODWORD(v13.dwTotalPageFile) ^ LODWORD(v13.dwAvailPhys);
  *(_DWORD *)((char *)v14 + 2) ^= LODWORD(v13.dwTotalVirtual) ^ LODWORD(v13.dwAvailPageFile);
  v14[0] ^= LODWORD(v13.dwAvailVirtual);
  if ( AllocateLocallyUniqueId((PLUID)&PerformanceCount) )
  {
    v14[0] ^= PerformanceCount.LowPart;
    *(_DWORD *)((char *)v14 + 2) ^= PerformanceCount.HighPart;
  }
  if ( GetDiskFreeSpaceA("c:\\", &SectorsPerCluster, &BytesPerSector, &NumberOfFreeClusters, &TotalNumberOfClusters) )
  {
    *(_DWORD *)((char *)v14 + 2) ^= TotalNumberOfClusters * BytesPerSector * SectorsPerCluster;
    v14[0] ^= NumberOfFreeClusters * BytesPerSector * SectorsPerCluster;
  }
  LOBYTE(v14[0]) |= 0x80u;
  *(_DWORD *)a1 = v14[0];
  *((_WORD *)a1 + 2) = v14[1];
  return 1824;
}

```

## disassembly

```asm
0x383ad3230  mov     [rsp-8+arg_8], rbx
0x383ad3235  mov     [rsp-8+arg_10], rdi
0x383ad323a  push    rbp
0x383ad323b  lea     rbp, [rsp-57h]
0x383ad3240  sub     rsp, 0C0h
0x383ad3247  mov     rax, cs:__security_cookie
0x383ad324e  xor     rax, rsp
0x383ad3251  mov     [rbp+57h+var_10], rax
0x383ad3255  xor     eax, eax
0x383ad3257  mov     rbx, rcx
0x383ad325a  lea     rdx, [rbp+57h+nSize]; nSize
0x383ad325e  lea     rcx, [rbp+57h+Buffer]; lpBuffer
0x383ad3262  xor     edi, edi
0x383ad3264  mov     byte ptr [rbp+57h+var_38], 0
0x383ad3268  mov     [rbp+57h+var_38+1], eax
0x383ad326b  mov     [rbp+57h+var_33], al
0x383ad326e  mov     [rbp+57h+var_2E], rax
0x383ad3272  mov     [rbp+57h+Buffer], di
0x383ad3276  mov     [rbp+57h+var_26], rax
0x383ad327a  mov     [rbp+57h+var_1E], rax
0x383ad327e  mov     [rbp+57h+var_16], eax
0x383ad3281  mov     [rbp+57h+var_12], ax
0x383ad3285  mov     [rbp+57h+nSize], 10h
0x383ad328c  call    cs:__imp_GetComputerNameW
0x383ad3292  test    eax, eax
0x383ad3294  jz      short loc_383AD32D5
0x383ad3296  mov     edx, edi
0x383ad3298  lea     r8, [rbp+57h+Buffer]
0x383ad329c  mov     [rbp+57h+nSize], edx
0x383ad329f  cmp     [rbp+57h+Buffer], dx
0x383ad32a3  jz      short loc_383AD32D5
0x383ad32a5  nop     word ptr [rax+rax+00000000h]
0x383ad32b0  mov     eax, edx
0x383ad32b2  inc     edx
0x383ad32b4  add     r8, 2
0x383ad32b8  lea     rcx, [rbp+57h+var_38]
0x383ad32bc  add     rcx, rax
0x383ad32bf  movzx   eax, byte ptr [r8-2]
0x383ad32c4  xor     [rcx], al
0x383ad32c6  cmp     edx, 6
0x383ad32c9  cmovnb  edx, edi
0x383ad32cc  cmp     [r8], di
0x383ad32d0  jnz     short loc_383AD32B0
0x383ad32d2  mov     [rbp+57h+nSize], edx
0x383ad32d5  lea     rcx, [rbp+57h+PerformanceCount]; lpPerformanceCount
0x383ad32d9  call    cs:__imp_QueryPerformanceCounter
0x383ad32df  test    eax, eax
0x383ad32e1  jz      short loc_383AD32FD
0x383ad32e3  mov     ecx, [rbp+57h+var_38+2]
0x383ad32e6  mov     rax, qword ptr [rbp+57h+PerformanceCount]
0x383ad32ea  mov     edx, dword ptr [rbp+57h+PerformanceCount+4]
0x383ad32ed  xor     ecx, eax
0x383ad32ef  xor     ecx, edx
0x383ad32f1  mov     [rbp+57h+var_38+2], ecx
0x383ad32f4  mov     ecx, [rbp+57h+var_38]
0x383ad32f7  xor     ecx, eax
0x383ad32f9  xor     ecx, edx
0x383ad32fb  jmp     short loc_383AD3300
0x383ad32fd  mov     ecx, [rbp+57h+var_38]
0x383ad3300  lea     rax, [rbp+57h+var_38]
0x383ad3304  mov     [rbp+57h+var_70.dwLength], 38h ; '8'
0x383ad330b  xor     ecx, eax
0x383ad330d  lea     rax, [rbp+57h+var_38]
0x383ad3311  mov     [rbp+57h+var_38], ecx
0x383ad3314  xor     [rbp+57h+var_38+2], eax
0x383ad3317  lea     rcx, [rbp+57h+var_70]; lpBuffer
0x383ad331b  call    cs:__imp_GlobalMemoryStatus
0x383ad3321  mov     eax, dword ptr [rbp+57h+var_70.dwTotalPhys]
0x383ad3324  mov     r11d, [rbp+57h+var_70.dwMemoryLoad]
0x383ad3328  xor     [rbp+57h+var_38], r11d
0x383ad332c  xor     [rbp+57h+var_38+2], eax
0x383ad332f  mov     eax, [rbp+57h+var_38]
0x383ad3332  xor     eax, dword ptr [rbp+57h+var_70.dwAvailPhys]
0x383ad3335  lea     rcx, [rbp+57h+PerformanceCount]; Luid
0x383ad3339  xor     eax, dword ptr [rbp+57h+var_70.dwTotalPageFile]
0x383ad333c  mov     [rbp+57h+var_38], eax
0x383ad333f  mov     eax, [rbp+57h+var_38+2]
0x383ad3342  xor     eax, dword ptr [rbp+57h+var_70.dwAvailPageFile]
0x383ad3345  xor     eax, dword ptr [rbp+57h+var_70.dwTotalVirtual]
0x383ad3348  mov     [rbp+57h+var_38+2], eax
0x383ad334b  mov     eax, dword ptr [rbp+57h+var_70.dwAvailVirtual]
0x383ad334e  xor     [rbp+57h+var_38], eax
0x383ad3351  call    cs:__imp_AllocateLocallyUniqueId
0x383ad3357  test    eax, eax
0x383ad3359  jz      short loc_383AD3367
0x383ad335b  mov     eax, dword ptr [rbp+57h+PerformanceCount]
0x383ad335e  xor     [rbp+57h+var_38], eax
0x383ad3361  mov     eax, dword ptr [rbp+57h+PerformanceCount+4]
0x383ad3364  xor     [rbp+57h+var_38+2], eax
0x383ad3367  lea     rax, [rbp+57h+TotalNumberOfClusters]
0x383ad336b  lea     r9, [rbp+57h+NumberOfFreeClusters]; lpNumberOfFreeClusters
0x383ad336f  lea     r8, [rbp+57h+BytesPerSector]; lpBytesPerSector
0x383ad3373  lea     rdx, [rbp+57h+SectorsPerCluster]; lpSectorsPerCluster
0x383ad3377  lea     rcx, RootPathName; "c:\\"
0x383ad337e  mov     [rsp+0C0h+lpTotalNumberOfClusters], rax; lpTotalNumberOfClusters
0x383ad3383  call    cs:__imp_GetDiskFreeSpaceA
0x383ad3389  test    eax, eax
0x383ad338b  jz      short loc_383AD33A4
0x383ad338d  mov     ecx, [rbp+57h+SectorsPerCluster]
0x383ad3390  imul    ecx, [rbp+57h+BytesPerSector]
0x383ad3394  mov     eax, ecx
0x383ad3396  imul    ecx, [rbp+57h+NumberOfFreeClusters]
0x383ad339a  imul    eax, [rbp+57h+TotalNumberOfClusters]
0x383ad339e  xor     [rbp+57h+var_38+2], eax
0x383ad33a1  xor     [rbp+57h+var_38], ecx
0x383ad33a4  or      byte ptr [rbp+57h+var_38], 80h
0x383ad33a8  mov     eax, [rbp+57h+var_38]
0x383ad33ab  mov     [rbx], eax
0x383ad33ad  movzx   eax, word ptr [rbp+23h]
0x383ad33b1  mov     [rbx+4], ax
0x383ad33b5  mov     eax, 720h
0x383ad33ba  mov     rcx, [rbp+57h+var_10]
0x383ad33be  xor     rcx, rsp; StackCookie
0x383ad33c1  call    __security_check_cookie
0x383ad33c6  lea     r11, [rsp+0C0h+var_s0]
0x383ad33ce  mov     rbx, [r11+18h]
0x383ad33d2  mov     rdi, [r11+20h]
0x383ad33d6  mov     rsp, r11
0x383ad33d9  pop     rbp
0x383ad33da  retn
```
