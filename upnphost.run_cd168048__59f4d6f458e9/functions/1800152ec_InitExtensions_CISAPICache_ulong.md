# InitExtensions(CISAPICache * *,ulong *)

- ea: `0x1800152ec`
- end: `0x180015417`
- name: `?InitExtensions@@YAHPEAPEAVCISAPICache@@PEAK@Z`
- size: `299`
- prototype: `__int64 __fastcall(struct CISAPICache **, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180014580`

## callees

- `0x1800152ec`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800153f8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800153f8`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180015398`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180015398`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800153be`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800153be`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800153e3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800153e3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180015338`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180015338`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001537b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001537b`

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
0x1800152ec  mov     [rsp-18h+arg_10], rbx
0x1800152f1  push    rbp
0x1800152f2  push    rsi
0x1800152f3  push    rdi
0x1800152f4  mov     rbp, rsp
0x1800152f7  sub     rsp, 50h
0x1800152fb  mov     rsi, rdx
0x1800152fe  mov     [rbp+hKey], 0
0x180015306  mov     rdi, rcx
0x180015309  mov     [rbp+var_18], 0
0x180015310  lea     rax, [rbp+hKey]
0x180015314  mov     [rbp+Block], 0
0x18001531c  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Ole"
0x180015323  mov     [rsp+50h+phkResult], rax; phkResult
0x180015328  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001532f  mov     r9d, 20019h; samDesired
0x180015335  xor     r8d, r8d; ulOptions
0x180015338  call    cs:__imp_RegOpenKeyExW
0x18001533f  nop     dword ptr [rax+rax+00h]
0x180015344  mov     rcx, [rbp+hKey]; hKey
0x180015348  mov     ebx, 927C0h
0x18001534d  mov     [rbp+Data], ebx
0x180015350  test    rcx, rcx
0x180015353  jz      short loc_18001538E
0x180015355  lea     rax, [rbp+cbData]
0x180015359  mov     [rbp+cbData], 4
0x180015360  mov     [rsp+50h+lpcbData], rax; lpcbData
0x180015365  lea     rdx, aFreetimeout; "FreeTimeout"
0x18001536c  lea     rax, [rbp+Data]
0x180015370  xor     r9d, r9d; lpType
0x180015373  xor     r8d, r8d; lpReserved
0x180015376  mov     [rsp+50h+phkResult], rax; lpData
0x18001537b  call    cs:__imp_RegQueryValueExW
0x180015382  nop     dword ptr [rax+rax+00h]
0x180015387  test    eax, eax
0x180015389  jnz     short loc_18001538E
0x18001538b  mov     ebx, [rbp+Data]
0x18001538e  lea     eax, [rbx+rbx*2]
0x180015391  mov     ecx, 30h ; '0'; Size
0x180015396  mov     [rsi], eax
0x180015398  call    cs:__imp_malloc
0x18001539f  nop     dword ptr [rax+rax+00h]
0x1800153a4  mov     rbx, rax
0x1800153a7  test    rax, rax
0x1800153aa  jz      short loc_1800153CC
0x1800153ac  xorps   xmm0, xmm0
0x1800153af  lea     rcx, [rax+8]; lpCriticalSection
0x1800153b3  movups  xmmword ptr [rax], xmm0
0x1800153b6  movups  xmmword ptr [rax+10h], xmm0
0x1800153ba  movups  xmmword ptr [rax+20h], xmm0
0x1800153be  call    cs:__imp_InitializeCriticalSection
0x1800153c5  nop     dword ptr [rax+rax+00h]
0x1800153ca  jmp     short loc_1800153CE
0x1800153cc  xor     ebx, ebx
0x1800153ce  mov     rcx, [rbp+hKey]; hKey
0x1800153d2  mov     [rdi], rbx
0x1800153d5  xor     edi, edi
0x1800153d7  test    rbx, rbx
0x1800153da  setnz   dil
0x1800153de  test    rcx, rcx
0x1800153e1  jz      short loc_1800153EF
0x1800153e3  call    cs:__imp_RegCloseKey
0x1800153ea  nop     dword ptr [rax+rax+00h]
0x1800153ef  mov     rcx, [rbp+Block]; Block
0x1800153f3  test    rcx, rcx
0x1800153f6  jz      short loc_180015404
0x1800153f8  call    cs:__imp_free
0x1800153ff  nop     dword ptr [rax+rax+00h]
0x180015404  mov     rbx, [rsp+50h+arg_10]
0x18001540c  mov     eax, edi
0x18001540e  add     rsp, 50h
0x180015412  pop     rdi
0x180015413  pop     rsi
0x180015414  pop     rbp
0x180015415  retn
```
