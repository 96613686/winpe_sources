# InitExtensions(CISAPICache * *,ulong *)

- ea: `0x1800200e0`
- end: `0x1800201e6`
- name: `?InitExtensions@@YAHPEAPEAVCISAPICache@@PEAK@Z`
- size: `262`
- prototype: `__int64 __fastcall(struct CISAPICache **, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001f41c`

## callees

- `0x1800200e0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800201ce`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800201ce`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180020180`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180020180`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800201a0`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800201a0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800201bf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800201bf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002012c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002012c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180020169`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180020169`

## pseudocode

```c
_BOOL8 __fastcall InitExtensions(struct CISAPICache **a1, unsigned int *a2)
{
  int v4; // ebx
  char *v5; // rax
  struct CISAPICache *v6; // rbx
  HKEY v7; // rcx
  HKEY hKey; // [rsp+30h] [rbp-20h] BYREF
  int v10; // [rsp+38h] [rbp-18h]
  void *Block; // [rsp+40h] [rbp-10h]
  int Data; // [rsp+70h] [rbp+20h] BYREF
  DWORD cbData; // [rsp+78h] [rbp+28h] BYREF

  hKey = 0;
  v10 = 0;
  Block = 0;
  RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Ole", 0, 0x20019u, &hKey);
  v4 = 600000;
  Data = 600000;
  if ( hKey )
  {
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"FreeTimeout", 0, 0, (LPBYTE)&Data, &cbData) )
      v4 = Data;
  }
  *a2 = 3 * v4;
  v5 = (char *)malloc(0x30u);
  v6 = (struct CISAPICache *)v5;
  if ( v5 )
  {
    *(_OWORD *)v5 = 0;
    *((_OWORD *)v5 + 1) = 0;
    *((_OWORD *)v5 + 2) = 0;
    InitializeCriticalSection((LPCRITICAL_SECTION)(v5 + 8));
  }
  else
  {
    v6 = 0;
  }
  v7 = hKey;
  *a1 = v6;
  if ( v7 )
    RegCloseKey(v7);
  if ( Block )
    free(Block);
  return v6 != 0;
}

```

## disassembly

```asm
0x1800200e0  mov     [rsp-18h+arg_10], rbx
0x1800200e5  push    rbp
0x1800200e6  push    rsi
0x1800200e7  push    rdi
0x1800200e8  mov     rbp, rsp
0x1800200eb  sub     rsp, 50h
0x1800200ef  mov     rsi, rdx
0x1800200f2  mov     [rbp+hKey], 0
0x1800200fa  mov     rdi, rcx
0x1800200fd  mov     [rbp+var_18], 0
0x180020104  lea     rax, [rbp+hKey]
0x180020108  mov     [rbp+Block], 0
0x180020110  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Ole"
0x180020117  mov     [rsp+50h+phkResult], rax; phkResult
0x18002011c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180020123  mov     r9d, 20019h; samDesired
0x180020129  xor     r8d, r8d; ulOptions
0x18002012c  call    cs:__imp_RegOpenKeyExW
0x180020132  mov     rcx, [rbp+hKey]; hKey
0x180020136  mov     ebx, 927C0h
0x18002013b  mov     [rbp+Data], ebx
0x18002013e  test    rcx, rcx
0x180020141  jz      short loc_180020176
0x180020143  lea     rax, [rbp+cbData]
0x180020147  mov     [rbp+cbData], 4
0x18002014e  mov     [rsp+50h+lpcbData], rax; lpcbData
0x180020153  lea     rdx, aFreetimeout; "FreeTimeout"
0x18002015a  lea     rax, [rbp+Data]
0x18002015e  xor     r9d, r9d; lpType
0x180020161  xor     r8d, r8d; lpReserved
0x180020164  mov     [rsp+50h+phkResult], rax; lpData
0x180020169  call    cs:__imp_RegQueryValueExW
0x18002016f  test    eax, eax
0x180020171  jnz     short loc_180020176
0x180020173  mov     ebx, [rbp+Data]
0x180020176  lea     eax, [rbx+rbx*2]
0x180020179  mov     ecx, 30h ; '0'; Size
0x18002017e  mov     [rsi], eax
0x180020180  call    cs:__imp_malloc
0x180020186  mov     rbx, rax
0x180020189  test    rax, rax
0x18002018c  jz      short loc_1800201A8
0x18002018e  xorps   xmm0, xmm0
0x180020191  lea     rcx, [rax+8]; lpCriticalSection
0x180020195  movups  xmmword ptr [rax], xmm0
0x180020198  movups  xmmword ptr [rax+10h], xmm0
0x18002019c  movups  xmmword ptr [rax+20h], xmm0
0x1800201a0  call    cs:__imp_InitializeCriticalSection
0x1800201a6  jmp     short loc_1800201AA
0x1800201a8  xor     ebx, ebx
0x1800201aa  mov     rcx, [rbp+hKey]; hKey
0x1800201ae  mov     [rdi], rbx
0x1800201b1  xor     edi, edi
0x1800201b3  test    rbx, rbx
0x1800201b6  setnz   dil
0x1800201ba  test    rcx, rcx
0x1800201bd  jz      short loc_1800201C5
0x1800201bf  call    cs:__imp_RegCloseKey
0x1800201c5  mov     rcx, [rbp+Block]; Block
0x1800201c9  test    rcx, rcx
0x1800201cc  jz      short loc_1800201D4
0x1800201ce  call    cs:__imp_free
0x1800201d4  mov     rbx, [rsp+50h+arg_10]
0x1800201dc  mov     eax, edi
0x1800201de  add     rsp, 50h
0x1800201e2  pop     rdi
0x1800201e3  pop     rsi
0x1800201e4  pop     rbp
0x1800201e5  retn
```
