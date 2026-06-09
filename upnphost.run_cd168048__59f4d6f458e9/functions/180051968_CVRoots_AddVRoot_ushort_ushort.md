# CVRoots::AddVRoot(ushort *,ushort *)

- ea: `0x180051968`
- end: `0x180051b53`
- name: `?AddVRoot@CVRoots@@QEAAHPEAG0@Z`
- size: `491`
- prototype: `__int64 __fastcall(CVRoots *__hidden this, LPCWCH lpWideCharStr, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180051524`

## callees

- `0x18001197c`
- `0x180012c40`
- `0x18001b2d0`
- `0x18001bbc0`
- `0x1800200f4`
- `0x180029740`
- `0x180032c6c`
- `0x18003bb6c`
- `0x180051968`
- `0x180052058`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180051b1f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180051b1f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800519a7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800519a7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180051b2e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180051b2e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180051ab8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180051ac9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180051ab8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180051ac9`

## string_xrefs

- `0x1800519f4`: `CVRoots::AddVRoot - already present`

## pseudocode

```c
char *__fastcall CVRoots::AddVRoot(struct _RTL_CRITICAL_SECTION *this, WCHAR *lpWideCharStr, unsigned __int16 *a3)
{
  char *result; // rax
  char *v7; // rsi
  __int64 v8; // rbx
  void *v9; // r9
  int DebugInfo; // ecx
  unsigned __int8 *v11; // r8
  char *v12; // rax
  int v13; // ecx
  int v14; // ecx
  int v15; // ebx
  __int64 v16; // r8
  __int64 v17; // r9
  struct _SECURITY_ATTRIBUTES *v18; // [rsp+20h] [rbp-48h]
  HKEY v19; // [rsp+40h] [rbp-28h] BYREF
  HKEY hKey; // [rsp+88h] [rbp+20h] BYREF

  result = SzFromWsz(lpWideCharStr);
  v7 = result;
  if ( result )
  {
    v8 = -1;
    do
      ++v8;
    while ( result[v8] );
    EnterCriticalSection(this);
    if ( CVRoots::MatchVRoot((CVRoots *)this, v7, v8) )
    {
      if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          14,
          (unsigned int)WPP_f28cf248efbf3aa3b14f0d26735e5363_Traceguids,
          (unsigned int)"CVRoots::AddVRoot - already present",
          5);
    }
    else
    {
      DebugInfo = (int)this[1].DebugInfo;
      v11 = *(unsigned __int8 **)&this[1].LockCount;
      LODWORD(this[1].DebugInfo) = DebugInfo + 1;
      v12 = (char *)svsutil_ReAlloc((unsigned int)(56 * DebugInfo), 56 * DebugInfo + 56, v11, v9);
      v13 = (int)this[1].DebugInfo;
      *(_QWORD *)&this[1].LockCount = v12;
      v14 = v13 - 1;
      if ( v14 && v12 && CVRoots::FillVRoot((CVRoots *)v14, (struct VROOTINFO *)&v12[56 * v14], lpWideCharStr, a3) )
      {
        v19 = 0;
        hKey = 0;
        v15 = HrCreateOrOpenVRootsKey(&v19);
        if ( v15 < 0 )
          goto LABEL_17;
        v15 = HrRegCreateKeyEx(v19, lpWideCharStr, v16, v17, v18, &hKey, 0);
        if ( v15 >= 0 )
        {
          v15 = HrRegSetSz(hKey, 0, a3);
          RegCloseKey(hKey);
        }
        RegCloseKey(v19);
        if ( v15 < 0 )
        {
LABEL_17:
          if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
            WPP_SF_sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              15,
              (unsigned int)WPP_f28cf248efbf3aa3b14f0d26735e5363_Traceguids,
              (unsigned int)"CVRoots::AddVRoot",
              v15);
        }
        else
        {
          CVRoots::Sort((CVRoots *)this);
        }
      }
    }
    free(v7);
    LeaveCriticalSection(this);
    return (char *)1;
  }
  return result;
}

```

## disassembly

```asm
0x180051968  mov     [rsp+arg_0], rbx
0x18005196d  mov     [rsp+arg_8], rbp
0x180051972  push    rsi
0x180051973  push    rdi
0x180051974  push    r14
0x180051976  sub     rsp, 50h
0x18005197a  mov     rdi, rcx
0x18005197d  mov     r14, r8
0x180051980  mov     rcx, rdx; lpWideCharStr
0x180051983  mov     rbp, rdx
0x180051986  call    ?SzFromWsz@@YAPEADPEBG@Z; SzFromWsz(ushort const *)
0x18005198b  mov     rsi, rax
0x18005198e  test    rax, rax
0x180051991  jz      loc_180051B3F
0x180051997  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18005199b  inc     rbx
0x18005199e  cmp     byte ptr [rax+rbx], 0
0x1800519a2  jnz     short loc_18005199B
0x1800519a4  mov     rcx, rdi; lpCriticalSection
0x1800519a7  call    cs:__imp_EnterCriticalSection
0x1800519ae  nop     dword ptr [rax+rax+00h]
0x1800519b3  mov     r8d, ebx; int
0x1800519b6  mov     rdx, rsi; char *
0x1800519b9  mov     rcx, rdi; this
0x1800519bc  call    ?MatchVRoot@CVRoots@@AEAAPEAUVROOTINFO@@PEBDH@Z; CVRoots::MatchVRoot(char const *,int)
0x1800519c1  test    rax, rax
0x1800519c4  jz      short loc_180051A00
0x1800519c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800519cd  lea     rax, WPP_GLOBAL_Control
0x1800519d4  cmp     rcx, rax
0x1800519d7  jz      loc_180051B1C
0x1800519dd  test    byte ptr [rcx+1Ch], 1
0x1800519e1  jz      loc_180051B1C
0x1800519e7  mov     edx, 0Eh
0x1800519ec  mov     dword ptr [rsp+68h+var_48], 80004005h
0x1800519f4  lea     r9, aCvrootsAddvroo_0; "CVRoots::AddVRoot - already present"
0x1800519fb  jmp     loc_180051B0C
0x180051a00  mov     ecx, [rdi+28h]
0x180051a03  mov     r8, [rdi+30h]; unsigned __int8 *
0x180051a07  lea     eax, [rcx+1]
0x180051a0a  imul    ecx, 38h ; '8'; Size
0x180051a0d  mov     [rdi+28h], eax
0x180051a10  lea     edx, [rcx+38h]; unsigned int
0x180051a13  call    ?svsutil_ReAlloc@@YAPEAXKKPEAEPEAX@Z; svsutil_ReAlloc(ulong,ulong,uchar *,void *)
0x180051a18  mov     ecx, [rdi+28h]
0x180051a1b  mov     [rdi+30h], rax
0x180051a1f  sub     ecx, 1
0x180051a22  jz      loc_180051B1C
0x180051a28  test    rax, rax
0x180051a2b  jz      loc_180051B1C
0x180051a31  movsxd  rcx, ecx; this
0x180051a34  mov     r9, r14; unsigned __int16 *
0x180051a37  imul    rdx, rcx, 38h ; '8'
0x180051a3b  mov     r8, rbp; unsigned __int16 *
0x180051a3e  add     rdx, rax; struct VROOTINFO *
0x180051a41  call    ?FillVRoot@CVRoots@@AEAAHPEAUVROOTINFO@@PEAG1@Z; CVRoots::FillVRoot(VROOTINFO *,ushort *,ushort *)
0x180051a46  test    eax, eax
0x180051a48  jz      loc_180051B1C
0x180051a4e  lea     rcx, [rsp+68h+var_28]; HKEY *
0x180051a53  mov     [rsp+68h+var_28], 0
0x180051a5c  mov     [rsp+68h+hKey], 0
0x180051a68  call    ?HrCreateOrOpenVRootsKey@@YAJPEAPEAUHKEY__@@@Z; HrCreateOrOpenVRootsKey(HKEY__ * *)
0x180051a6d  mov     ebx, eax
0x180051a6f  test    eax, eax
0x180051a71  js      short loc_180051AE3
0x180051a73  mov     rcx, [rsp+68h+var_28]; HKEY
0x180051a78  lea     rax, [rsp+68h+hKey]
0x180051a80  mov     [rsp+68h+var_38], 0; unsigned int *
0x180051a89  mov     rdx, rbp; unsigned __int16 *
0x180051a8c  mov     [rsp+68h+var_40], rax; HKEY *
0x180051a91  call    ?HrRegCreateKeyEx@@YAJPEAUHKEY__@@PEBGKKPEAU_SECURITY_ATTRIBUTES@@PEAPEAU1@PEAK@Z; HrRegCreateKeyEx(HKEY__ *,ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *,HKEY__ * *,ulong *)
0x180051a96  mov     ebx, eax
0x180051a98  test    eax, eax
0x180051a9a  js      short loc_180051AC4
0x180051a9c  mov     rcx, [rsp+68h+hKey]; HKEY
0x180051aa4  mov     r8, r14; unsigned __int16 *
0x180051aa7  xor     edx, edx; unsigned __int16 *
0x180051aa9  call    ?HrRegSetSz@@YAJPEAUHKEY__@@PEBG1@Z; HrRegSetSz(HKEY__ *,ushort const *,ushort const *)
0x180051aae  mov     rcx, [rsp+68h+hKey]; hKey
0x180051ab6  mov     ebx, eax
0x180051ab8  call    cs:__imp_RegCloseKey
0x180051abf  nop     dword ptr [rax+rax+00h]
0x180051ac4  mov     rcx, [rsp+68h+var_28]; hKey
0x180051ac9  call    cs:__imp_RegCloseKey
0x180051ad0  nop     dword ptr [rax+rax+00h]
0x180051ad5  test    ebx, ebx
0x180051ad7  js      short loc_180051AE3
0x180051ad9  mov     rcx, rdi; this
0x180051adc  call    ?Sort@CVRoots@@AEAAXXZ; CVRoots::Sort(void)
0x180051ae1  jmp     short loc_180051B1C
0x180051ae3  mov     rcx, cs:WPP_GLOBAL_Control
0x180051aea  lea     rax, WPP_GLOBAL_Control
0x180051af1  cmp     rcx, rax
0x180051af4  jz      short loc_180051B1C
0x180051af6  test    byte ptr [rcx+1Ch], 1
0x180051afa  jz      short loc_180051B1C
0x180051afc  mov     edx, 0Fh
0x180051b01  mov     dword ptr [rsp+68h+var_48], ebx
0x180051b05  lea     r9, aCvrootsAddvroo; "CVRoots::AddVRoot"
0x180051b0c  mov     rcx, [rcx+10h]
0x180051b10  lea     r8, WPP_f28cf248efbf3aa3b14f0d26735e5363_Traceguids
0x180051b17  call    WPP_SF_sd
0x180051b1c  mov     rcx, rsi; Block
0x180051b1f  call    cs:__imp_free
0x180051b26  nop     dword ptr [rax+rax+00h]
0x180051b2b  mov     rcx, rdi; lpCriticalSection
0x180051b2e  call    cs:__imp_LeaveCriticalSection
0x180051b35  nop     dword ptr [rax+rax+00h]
0x180051b3a  mov     eax, 1
0x180051b3f  mov     rbx, [rsp+68h+arg_0]
0x180051b44  mov     rbp, [rsp+68h+arg_8]
0x180051b49  add     rsp, 50h
0x180051b4d  pop     r14
0x180051b4f  pop     rdi
0x180051b50  pop     rsi
0x180051b51  retn
```
