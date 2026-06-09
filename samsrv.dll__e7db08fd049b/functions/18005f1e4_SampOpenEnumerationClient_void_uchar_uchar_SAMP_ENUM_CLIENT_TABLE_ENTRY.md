# SampOpenEnumerationClient(void *,uchar,uchar *,_SAMP_ENUM_CLIENT_TABLE_ENTRY * *)

- ea: `0x18005f1e4`
- end: `0x18005f40e`
- name: `?SampOpenEnumerationClient@@YAJPEAXEPEAEPEAPEAU_SAMP_ENUM_CLIENT_TABLE_ENTRY@@@Z`
- size: `554`
- prototype: `__int64 __fastcall(void *Src, unsigned __int8, unsigned __int8 *, struct _SAMP_ENUM_CLIENT_TABLE_ENTRY **)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18005f0b4`
- `0x18005f710`

## callees

- `0x180027e24`
- `0x1800372ac`
- `0x18004e28c`
- `0x18005e998`
- `0x18005f1e4`
- `0x18005fa14`
- `0x1800bb788`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005f346`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005f346`
- `ntdll!RtlLeaveCriticalSection` at `0x18005f30b`
- `ntdll!RtlLeaveCriticalSection` at `0x18005f30b`
- `ntdll!RtlEnterCriticalSection` at `0x18005f295`
- `ntdll!RtlEnterCriticalSection` at `0x18005f295`
- `ntdll!RtlLengthSid` at `0x18005f21e`
- `ntdll!RtlLengthSid` at `0x18005f263`
- `ntdll!RtlLengthSid` at `0x18005f21e`
- `ntdll!RtlLengthSid` at `0x18005f263`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005f22b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005f22b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005f3ae`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005f3c1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005f3ae`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005f3c1`

## pseudocode

```c
__int64 __fastcall SampOpenEnumerationClient(
        void *Src,
        char a2,
        unsigned __int8 *a3,
        struct _SAMP_ENUM_CLIENT_TABLE_ENTRY **a4)
{
  ULONG v7; // eax
  HLOCAL v8; // r12
  PUNICODE_STRING v9; // rcx
  int EnumerationClient; // ebp
  __int64 v11; // rdx
  __int64 v12; // r9
  ULONG v13; // eax
  struct _SAMP_ENUM_CLIENT_TABLE_ENTRY *v14; // rdi
  int *v15; // rbx
  int v16; // ebx
  void *pSid; // rdi
  DWORD CurrentThreadId; // eax
  int v19; // r8d
  HLOCAL hMem; // [rsp+40h] [rbp-38h] BYREF

  hMem = 0;
  *a4 = 0;
  v7 = RtlLengthSid(Src);
  v8 = LocalAlloc(0x40u, v7);
  if ( v8 )
  {
    v13 = RtlLengthSid(Src);
    memcpy_0(v8, Src, v13);
    EnumerationClient = SampCreateEnumerationClient(v8, (struct _SAMP_ENUM_CLIENT_TABLE_ENTRY **)&hMem);
    if ( EnumerationClient < 0 )
      goto LABEL_17;
    RtlEnterCriticalSection(&SampActiveEnumerationClientTableLock);
    v14 = (struct _SAMP_ENUM_CLIENT_TABLE_ENTRY *)SampLookupElementInTable(
                                                    (struct _RTL_GENERIC_TABLE2 *)&SampActiveEnumerationClientTable,
                                                    hMem);
    v15 = (int *)((char *)v14 + 8);
    if ( v14 )
    {
      if ( (unsigned int)*v15 < 0x400 )
      {
        if ( a2 )
          ++*v15;
        *a4 = v14;
        *a3 = 0;
      }
      else
      {
        EnumerationClient = -1073741670;
      }
    }
    else
    {
      EnumerationClient = -1073741670;
    }
    RtlLeaveCriticalSection(&SampActiveEnumerationClientTableLock);
    if ( EnumerationClient < 0 )
    {
LABEL_17:
      if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20) != 0
        && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 4u )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control[3].Buffer,
          16,
          WPP_e06bfd625d253087cbb49159475169cf_Traceguids,
          (unsigned int)EnumerationClient);
      }
    }
    else if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20) != 0
           && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 4u )
    {
      v16 = *v15;
      pSid = *(void **)v14;
      CurrentThreadId = GetCurrentThreadId();
      WPP_SF_dS_sid_d((int)WPP_GLOBAL_Control[3].Buffer, 15, v19, CurrentThreadId, (__int64)L"EXISTING", pSid, v16);
    }
    LocalFree(v8);
    if ( hMem )
      LocalFree(hMem);
    v9 = WPP_GLOBAL_Control;
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    {
      v11 = 17;
      v12 = (unsigned int)EnumerationClient;
      goto LABEL_23;
    }
  }
  else
  {
    v9 = WPP_GLOBAL_Control;
    EnumerationClient = -1073741670;
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    {
      v11 = 14;
      v12 = 3221225626LL;
LABEL_23:
      WPP_SF_Dd(v9[3].Buffer, v11, WPP_e06bfd625d253087cbb49159475169cf_Traceguids, v12, EnumerationClient);
    }
  }
  return (unsigned int)EnumerationClient;
}

```

## disassembly

```asm
0x18005f1e4  mov     rax, rsp
0x18005f1e7  mov     [rax+8], rbx
0x18005f1eb  mov     [rax+10h], rbp
0x18005f1ef  mov     [rax+18h], r8
0x18005f1f3  push    rsi
0x18005f1f4  push    rdi
0x18005f1f5  push    r12
0x18005f1f7  push    r13
0x18005f1f9  push    r14
0x18005f1fb  sub     rsp, 50h
0x18005f1ff  xor     r14b, r14b
0x18005f202  mov     qword ptr [rax-38h], 0
0x18005f20a  mov     [rax+20h], r14b
0x18005f20e  mov     rsi, r9
0x18005f211  mov     r13b, dl
0x18005f214  mov     qword ptr [r9], 0
0x18005f21b  mov     rbx, rcx
0x18005f21e  call    cs:__imp_RtlLengthSid
0x18005f224  mov     edx, eax; uBytes
0x18005f226  mov     ecx, 40h ; '@'; uFlags
0x18005f22b  call    cs:__imp_LocalAlloc
0x18005f231  mov     r12, rax
0x18005f234  test    rax, rax
0x18005f237  jnz     short loc_18005F260
0x18005f239  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f240  mov     ebp, 0C000009Ah
0x18005f245  test    dword ptr [rcx+44h], 20000h
0x18005f24c  jz      loc_18005F3F3
0x18005f252  lea     edx, [rax+0Eh]
0x18005f255  mov     r9d, 0C000009Ah
0x18005f25b  jmp     loc_18005F3DF
0x18005f260  mov     rcx, rbx; Sid
0x18005f263  call    cs:__imp_RtlLengthSid
0x18005f269  mov     r8d, eax; Size
0x18005f26c  mov     rdx, rbx; Src
0x18005f26f  mov     rcx, r12; void *
0x18005f272  call    memcpy_0
0x18005f277  lea     rdx, [rsp+78h+hMem]; struct _SAMP_ENUM_CLIENT_TABLE_ENTRY **
0x18005f27c  mov     rcx, r12; void *
0x18005f27f  call    ?SampCreateEnumerationClient@@YAJPEAXPEAPEAU_SAMP_ENUM_CLIENT_TABLE_ENTRY@@@Z; SampCreateEnumerationClient(void *,_SAMP_ENUM_CLIENT_TABLE_ENTRY * *)
0x18005f284  mov     ebp, eax
0x18005f286  test    eax, eax
0x18005f288  js      loc_18005F374
0x18005f28e  lea     rcx, ?SampActiveEnumerationClientTableLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18005f295  call    cs:__imp_RtlEnterCriticalSection
0x18005f29b  mov     rdx, [rsp+78h+hMem]; void *
0x18005f2a0  lea     r9, [rsp+78h+arg_18]
0x18005f2a8  mov     r8d, 0FFFFh
0x18005f2ae  lea     rcx, ?SampActiveEnumerationClientTable@@3U_RTL_GENERIC_TABLE2@@A; struct _RTL_GENERIC_TABLE2 *
0x18005f2b5  call    SampLookupElementInTable
0x18005f2ba  mov     rdi, rax
0x18005f2bd  lea     rbx, [rax+8]
0x18005f2c1  test    rax, rax
0x18005f2c4  jnz     short loc_18005F2CD
0x18005f2c6  mov     ebp, 0C000009Ah
0x18005f2cb  jmp     short loc_18005F304
0x18005f2cd  mov     eax, [rbx]
0x18005f2cf  cmp     eax, 400h
0x18005f2d4  jb      short loc_18005F2E5
0x18005f2d6  mov     r14b, [rsp+78h+arg_18]
0x18005f2de  mov     ebp, 0C000009Ah
0x18005f2e3  jmp     short loc_18005F304
0x18005f2e5  test    r13b, r13b
0x18005f2e8  jz      short loc_18005F2EE
0x18005f2ea  inc     eax
0x18005f2ec  mov     [rbx], eax
0x18005f2ee  mov     rax, [rsp+78h+arg_10]
0x18005f2f6  mov     r14b, [rsp+78h+arg_18]
0x18005f2fe  mov     [rsi], rdi
0x18005f301  mov     [rax], r14b
0x18005f304  lea     rcx, ?SampActiveEnumerationClientTableLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18005f30b  call    cs:__imp_RtlLeaveCriticalSection
0x18005f311  test    ebp, ebp
0x18005f313  js      short loc_18005F374
0x18005f315  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f31c  test    byte ptr [rcx+44h], 20h
0x18005f320  jz      loc_18005F3A6
0x18005f326  cmp     byte ptr [rcx+41h], 4
0x18005f32a  jb      short loc_18005F3A6
0x18005f32c  mov     ebx, [rbx]
0x18005f32e  lea     rax, aExisting; "EXISTING"
0x18005f335  mov     rdi, [rdi]
0x18005f338  lea     rsi, aNew; "NEW"
0x18005f33f  test    r14b, r14b
0x18005f342  cmovz   rsi, rax
0x18005f346  call    cs:__imp_GetCurrentThreadId
0x18005f34c  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f353  mov     edx, 0Fh; int
0x18005f358  mov     dword ptr [rsp+78h+var_48], ebx; char
0x18005f35c  mov     r9d, eax; int
0x18005f35f  mov     [rsp+78h+pSid], rdi; pSid
0x18005f364  mov     [rsp+78h+var_58], rsi; __int64
0x18005f369  mov     rcx, [rcx+38h]; int
0x18005f36d  call    WPP_SF_dS_sid_d
0x18005f372  jmp     short loc_18005F39F
0x18005f374  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f37b  test    byte ptr [rcx+44h], 20h
0x18005f37f  jz      short loc_18005F3A6
0x18005f381  cmp     byte ptr [rcx+41h], 4
0x18005f385  jb      short loc_18005F3A6
0x18005f387  mov     rcx, [rcx+38h]
0x18005f38b  lea     r8, WPP_e06bfd625d253087cbb49159475169cf_Traceguids
0x18005f392  mov     edx, 10h
0x18005f397  mov     r9d, ebp
0x18005f39a  call    WPP_SF_d
0x18005f39f  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f3a6  test    r14b, r14b
0x18005f3a9  jnz     short loc_18005F3CE
0x18005f3ab  mov     rcx, r12; hMem
0x18005f3ae  call    cs:__imp_LocalFree
0x18005f3b4  cmp     [rsp+78h+hMem], 0
0x18005f3ba  jz      short loc_18005F3C7
0x18005f3bc  mov     rcx, [rsp+78h+hMem]; hMem
0x18005f3c1  call    cs:__imp_LocalFree
0x18005f3c7  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f3ce  test    dword ptr [rcx+44h], 20000h
0x18005f3d5  jz      short loc_18005F3F3
0x18005f3d7  mov     edx, 11h
0x18005f3dc  mov     r9d, ebp
0x18005f3df  mov     rcx, [rcx+38h]
0x18005f3e3  lea     r8, WPP_e06bfd625d253087cbb49159475169cf_Traceguids
0x18005f3ea  mov     dword ptr [rsp+78h+var_58], ebp
0x18005f3ee  call    WPP_SF_Dd
0x18005f3f3  lea     r11, [rsp+78h+var_28]
0x18005f3f8  mov     eax, ebp
0x18005f3fa  mov     rbx, [r11+30h]
0x18005f3fe  mov     rbp, [r11+38h]
0x18005f402  mov     rsp, r11
0x18005f405  pop     r14
0x18005f407  pop     r13
0x18005f409  pop     r12
0x18005f40b  pop     rdi
0x18005f40c  pop     rsi
0x18005f40d  retn
```
