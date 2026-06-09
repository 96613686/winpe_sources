# CVRoots::AddVRoot(ushort *,ushort *)

- ea: `0x18004e468`
- end: `0x18004e634`
- name: `?AddVRoot@CVRoots@@QEAAHPEAG0@Z`
- size: `460`
- prototype: `char *__fastcall(struct _RTL_CRITICAL_SECTION *this, WCHAR *lpWideCharStr, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004e060`

## callees

- `0x180006680`
- `0x180006f10`
- `0x18000db4c`
- `0x18001ca98`
- `0x18001d048`
- `0x180028500`
- `0x1800311bc`
- `0x1800395c0`
- `0x18004e468`
- `0x18004eb00`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18004e60d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18004e60d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004e4a7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004e4a7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004e616`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004e616`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004e5b2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004e5bd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004e5b2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004e5bd`

## string_xrefs

- `0x18004e4ee`: `CVRoots::AddVRoot - already present`

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
  unsigned int v16; // r8d
  unsigned int v17; // r9d
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
0x18004e468  mov     [rsp+arg_0], rbx
0x18004e46d  mov     [rsp+arg_8], rbp
0x18004e472  push    rsi
0x18004e473  push    rdi
0x18004e474  push    r14
0x18004e476  sub     rsp, 50h
0x18004e47a  mov     rdi, rcx
0x18004e47d  mov     r14, r8
0x18004e480  mov     rcx, rdx; lpWideCharStr
0x18004e483  mov     rbp, rdx
0x18004e486  call    ?SzFromWsz@@YAPEADPEBG@Z; SzFromWsz(ushort const *)
0x18004e48b  mov     rsi, rax
0x18004e48e  test    rax, rax
0x18004e491  jz      loc_18004E621
0x18004e497  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18004e49b  inc     rbx
0x18004e49e  cmp     byte ptr [rax+rbx], 0
0x18004e4a2  jnz     short loc_18004E49B
0x18004e4a4  mov     rcx, rdi; lpCriticalSection
0x18004e4a7  call    cs:__imp_EnterCriticalSection
0x18004e4ad  mov     r8d, ebx; int
0x18004e4b0  mov     rdx, rsi; char *
0x18004e4b3  mov     rcx, rdi; this
0x18004e4b6  call    ?MatchVRoot@CVRoots@@AEAAPEAUVROOTINFO@@PEBDH@Z; CVRoots::MatchVRoot(char const *,int)
0x18004e4bb  test    rax, rax
0x18004e4be  jz      short loc_18004E4FA
0x18004e4c0  mov     rcx, cs:WPP_GLOBAL_Control
0x18004e4c7  lea     rax, WPP_GLOBAL_Control
0x18004e4ce  cmp     rcx, rax
0x18004e4d1  jz      loc_18004E60A
0x18004e4d7  test    byte ptr [rcx+1Ch], 1
0x18004e4db  jz      loc_18004E60A
0x18004e4e1  mov     edx, 0Eh
0x18004e4e6  mov     dword ptr [rsp+68h+var_48], 80004005h
0x18004e4ee  lea     r9, aCvrootsAddvroo_0; "CVRoots::AddVRoot - already present"
0x18004e4f5  jmp     loc_18004E5FA
0x18004e4fa  mov     ecx, [rdi+28h]
0x18004e4fd  mov     r8, [rdi+30h]; unsigned __int8 *
0x18004e501  lea     eax, [rcx+1]
0x18004e504  imul    ecx, 38h ; '8'; Size
0x18004e507  mov     [rdi+28h], eax
0x18004e50a  lea     edx, [rcx+38h]; unsigned int
0x18004e50d  call    ?svsutil_ReAlloc@@YAPEAXKKPEAEPEAX@Z; svsutil_ReAlloc(ulong,ulong,uchar *,void *)
0x18004e512  mov     ecx, [rdi+28h]
0x18004e515  mov     [rdi+30h], rax
0x18004e519  sub     ecx, 1
0x18004e51c  jz      loc_18004E60A
0x18004e522  test    rax, rax
0x18004e525  jz      loc_18004E60A
0x18004e52b  movsxd  rcx, ecx; this
0x18004e52e  mov     r9, r14; unsigned __int16 *
0x18004e531  imul    rdx, rcx, 38h ; '8'
0x18004e535  mov     r8, rbp; unsigned __int16 *
0x18004e538  add     rdx, rax; struct VROOTINFO *
0x18004e53b  call    ?FillVRoot@CVRoots@@AEAAHPEAUVROOTINFO@@PEAG1@Z; CVRoots::FillVRoot(VROOTINFO *,ushort *,ushort *)
0x18004e540  test    eax, eax
0x18004e542  jz      loc_18004E60A
0x18004e548  lea     rcx, [rsp+68h+var_28]; HKEY *
0x18004e54d  mov     [rsp+68h+var_28], 0
0x18004e556  mov     [rsp+68h+hKey], 0
0x18004e562  call    ?HrCreateOrOpenVRootsKey@@YAJPEAPEAUHKEY__@@@Z; HrCreateOrOpenVRootsKey(HKEY__ * *)
0x18004e567  mov     ebx, eax
0x18004e569  test    eax, eax
0x18004e56b  js      short loc_18004E5D1
0x18004e56d  mov     rcx, [rsp+68h+var_28]; HKEY
0x18004e572  lea     rax, [rsp+68h+hKey]
0x18004e57a  mov     [rsp+68h+var_38], 0; unsigned int *
0x18004e583  mov     rdx, rbp; unsigned __int16 *
0x18004e586  mov     [rsp+68h+var_40], rax; HKEY *
0x18004e58b  call    ?HrRegCreateKeyEx@@YAJPEAUHKEY__@@PEBGKKPEAU_SECURITY_ATTRIBUTES@@PEAPEAU1@PEAK@Z; HrRegCreateKeyEx(HKEY__ *,ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *,HKEY__ * *,ulong *)
0x18004e590  mov     ebx, eax
0x18004e592  test    eax, eax
0x18004e594  js      short loc_18004E5B8
0x18004e596  mov     rcx, [rsp+68h+hKey]; HKEY
0x18004e59e  mov     r8, r14; unsigned __int16 *
0x18004e5a1  xor     edx, edx; unsigned __int16 *
0x18004e5a3  call    ?HrRegSetSz@@YAJPEAUHKEY__@@PEBG1@Z; HrRegSetSz(HKEY__ *,ushort const *,ushort const *)
0x18004e5a8  mov     rcx, [rsp+68h+hKey]; hKey
0x18004e5b0  mov     ebx, eax
0x18004e5b2  call    cs:__imp_RegCloseKey
0x18004e5b8  mov     rcx, [rsp+68h+var_28]; hKey
0x18004e5bd  call    cs:__imp_RegCloseKey
0x18004e5c3  test    ebx, ebx
0x18004e5c5  js      short loc_18004E5D1
0x18004e5c7  mov     rcx, rdi; this
0x18004e5ca  call    ?Sort@CVRoots@@AEAAXXZ; CVRoots::Sort(void)
0x18004e5cf  jmp     short loc_18004E60A
0x18004e5d1  mov     rcx, cs:WPP_GLOBAL_Control
0x18004e5d8  lea     rax, WPP_GLOBAL_Control
0x18004e5df  cmp     rcx, rax
0x18004e5e2  jz      short loc_18004E60A
0x18004e5e4  test    byte ptr [rcx+1Ch], 1
0x18004e5e8  jz      short loc_18004E60A
0x18004e5ea  mov     edx, 0Fh
0x18004e5ef  mov     dword ptr [rsp+68h+var_48], ebx
0x18004e5f3  lea     r9, aCvrootsAddvroo; "CVRoots::AddVRoot"
0x18004e5fa  mov     rcx, [rcx+10h]
0x18004e5fe  lea     r8, WPP_f28cf248efbf3aa3b14f0d26735e5363_Traceguids
0x18004e605  call    WPP_SF_sd
0x18004e60a  mov     rcx, rsi; Block
0x18004e60d  call    cs:__imp_free
0x18004e613  mov     rcx, rdi; lpCriticalSection
0x18004e616  call    cs:__imp_LeaveCriticalSection
0x18004e61c  mov     eax, 1
0x18004e621  mov     rbx, [rsp+68h+arg_0]
0x18004e626  mov     rbp, [rsp+68h+arg_8]
0x18004e62b  add     rsp, 50h
0x18004e62f  pop     r14
0x18004e631  pop     rdi
0x18004e632  pop     rsi
0x18004e633  retn
```
