# CTrkConfiguration::Initialize(void)

- ea: `0x1800020a4`
- end: `0x1800022cd`
- name: `?Initialize@CTrkConfiguration@@QEAAXXZ`
- size: `553`
- prototype: `void __fastcall(CTrkConfiguration *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x180001e28`
- `0x180003b8c`

## callees

- `0x180002038`
- `0x1800020a4`
- `0x18000a09c`
- `0x180011000`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002233`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002233`

## string_xrefs

- `0x1800021db`: `Configuration`
- `0x1800020d4`: `System\CurrentControlSet\Services\TrkWks\Parameters`

## pseudocode

```c
void __fastcall CTrkConfiguration::Initialize(CTrkConfiguration *this)
{
  HKEY *phkResult; // rdi
  const WCHAR *v2; // r9
  __int64 v3; // r11
  WCHAR *v4; // rax
  __int64 v6; // r8
  __int64 v7; // rcx
  bool v8; // zf
  WCHAR *v9; // rcx
  __int64 v10; // r8
  WCHAR *v11; // rax
  __int64 v12; // r9
  const unsigned __int16 *v13; // r10
  __int64 v14; // rcx
  WCHAR *v15; // r8
  __int64 v16; // rax
  WCHAR *v17; // rcx
  __int64 v18; // r8
  WCHAR *v19; // rax
  __int64 v20; // r9
  WCHAR *v21; // rax
  const wchar_t *v22; // rcx
  __int64 v23; // rdx
  WCHAR *v24; // rcx
  LSTATUS v25; // eax
  const unsigned __int16 *v26; // r9
  WCHAR SubKey[264]; // [rsp+30h] [rbp-228h] BYREF

  phkResult = (HKEY *)((char *)this + 8);
  *(_DWORD *)this = 1;
  v2 = L"System\\CurrentControlSet\\Services\\TrkWks\\Parameters";
  v3 = 2147483646;
  *((_QWORD *)this + 1) = 0;
  v4 = SubKey;
  v6 = 260;
  v7 = 2147483646;
  do
  {
    if ( !v7 )
      break;
    if ( !*v2 )
      break;
    *v4++ = *v2++;
    --v7;
    --v6;
  }
  while ( v6 );
  v8 = v6 == 0;
  v9 = v4 - 1;
  v10 = 260;
  if ( !v8 )
    v9 = v4;
  v11 = SubKey;
  *v9 = 0;
  do
  {
    if ( !*v11 )
      break;
    ++v11;
    --v10;
  }
  while ( v10 );
  v12 = (260 - v10) & -(__int64)(v10 != 0);
  if ( v10 )
  {
    v13 = L"\\";
    v14 = 2147483646;
    v15 = &SubKey[v12];
    v16 = 260 - v12;
    if ( v12 != 260 )
    {
      do
      {
        if ( !v14 )
          break;
        if ( !*v13 )
          break;
        *v15++ = *v13++;
        --v14;
        --v16;
      }
      while ( v16 );
    }
    v17 = v15 - 1;
    if ( v16 )
      v17 = v15;
    *v17 = 0;
  }
  v18 = 260;
  v19 = SubKey;
  do
  {
    if ( !*v19 )
      break;
    ++v19;
    --v18;
  }
  while ( v18 );
  v20 = (260 - v18) & -(__int64)(v18 != 0);
  if ( v18 )
  {
    v21 = &SubKey[v20];
    v22 = L"Configuration";
    v23 = 260 - v20;
    if ( 260 != v20 )
    {
      do
      {
        if ( !v3 )
          break;
        if ( !*v22 )
          break;
        *v21++ = *v22++;
        --v3;
        --v23;
      }
      while ( v23 );
    }
    v24 = v21 - 1;
    if ( v23 )
      v24 = v21;
    *v24 = 0;
  }
  v25 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x2000000u, phkResult);
  if ( (v25 & 0xFFFFFFFC) == 0 && v25 != 1 )
  {
    CTrkConfiguration::Read(this, L"TrkDebugFlags", (unsigned int *)this + 5, 0x80000000);
    CTrkConfiguration::Read(this, L"DebugStoreFlags", (unsigned int *)this + 6, 1u);
    CTrkConfiguration::Read(this, L"TestFlags", (unsigned int *)this + 4, 0);
    CTrkConfiguration::Read(this, L"OperationLogName", (struct CMultiTsz *)CTrkConfiguration::_mtszOperationLog, v26);
  }
}

```

## disassembly

```asm
0x1800020a4  mov     [rsp+arg_8], rbx
0x1800020a9  mov     [rsp+arg_10], rsi
0x1800020ae  push    rdi
0x1800020af  sub     rsp, 250h
0x1800020b6  mov     rax, cs:__security_cookie
0x1800020bd  xor     rax, rsp
0x1800020c0  mov     [rsp+258h+var_18], rax
0x1800020c8  lea     rdi, [rcx+8]
0x1800020cc  mov     dword ptr [rcx], 1
0x1800020d2  xor     esi, esi
0x1800020d4  lea     r9, ?s_tszKeyNameLinkTrack@@3QBGB; "System\\CurrentControlSet\\Services\\Tr"...
0x1800020db  mov     r11d, 7FFFFFFEh
0x1800020e1  mov     [rdi], rsi
0x1800020e4  mov     edx, 104h
0x1800020e9  lea     rax, [rsp+258h+SubKey]
0x1800020ee  mov     rbx, rcx
0x1800020f1  mov     r8d, edx
0x1800020f4  mov     ecx, r11d
0x1800020f7  test    rcx, rcx
0x1800020fa  jz      short loc_18000211B
0x1800020fc  movzx   r10d, word ptr [r9]
0x180002100  test    r10w, r10w
0x180002104  jz      short loc_18000211B
0x180002106  mov     [rax], r10w
0x18000210a  add     r9, 2
0x18000210e  add     rax, 2
0x180002112  dec     rcx
0x180002115  sub     r8, 1
0x180002119  jnz     short loc_1800020F7
0x18000211b  test    r8, r8
0x18000211e  lea     rcx, [rax-2]
0x180002122  mov     r8, rdx
0x180002125  cmovnz  rcx, rax
0x180002129  lea     rax, [rsp+258h+SubKey]
0x18000212e  mov     [rcx], si
0x180002131  cmp     [rax], si
0x180002134  jz      short loc_180002140
0x180002136  add     rax, 2
0x18000213a  sub     r8, 1
0x18000213e  jnz     short loc_180002131
0x180002140  mov     rcx, rdx
0x180002143  mov     rax, r8
0x180002146  sub     rcx, r8
0x180002149  neg     rax
0x18000214c  sbb     r9, r9
0x18000214f  and     r9, rcx
0x180002152  test    r8, r8
0x180002155  jz      short loc_1800021A4
0x180002157  mov     rax, rdx
0x18000215a  lea     r8, [rsp+258h+SubKey]
0x18000215f  lea     r10, asc_180015BC8; "\\"
0x180002166  mov     rcx, r11
0x180002169  lea     r8, [r8+r9*2]
0x18000216d  sub     rax, r9
0x180002170  jz      short loc_180002196
0x180002172  test    rcx, rcx
0x180002175  jz      short loc_180002196
0x180002177  movzx   r9d, word ptr [r10]
0x18000217b  test    r9w, r9w
0x18000217f  jz      short loc_180002196
0x180002181  mov     [r8], r9w
0x180002185  add     r10, 2
0x180002189  add     r8, 2
0x18000218d  dec     rcx
0x180002190  sub     rax, 1
0x180002194  jnz     short loc_180002172
0x180002196  test    rax, rax
0x180002199  lea     rcx, [r8-2]
0x18000219d  cmovnz  rcx, r8
0x1800021a1  mov     [rcx], si
0x1800021a4  mov     r8, rdx
0x1800021a7  lea     rax, [rsp+258h+SubKey]
0x1800021ac  cmp     [rax], si
0x1800021af  jz      short loc_1800021BB
0x1800021b1  add     rax, 2
0x1800021b5  sub     r8, 1
0x1800021b9  jnz     short loc_1800021AC
0x1800021bb  mov     rcx, rdx
0x1800021be  mov     rax, r8
0x1800021c1  sub     rcx, r8
0x1800021c4  neg     rax
0x1800021c7  sbb     r9, r9
0x1800021ca  and     r9, rcx
0x1800021cd  test    r8, r8
0x1800021d0  jz      short loc_180002219
0x1800021d2  lea     rax, [rsp+258h+SubKey]
0x1800021d7  lea     rax, [rax+r9*2]
0x1800021db  lea     rcx, aConfiguration; "Configuration"
0x1800021e2  sub     rdx, r9
0x1800021e5  jz      short loc_18000220B
0x1800021e7  test    r11, r11
0x1800021ea  jz      short loc_18000220B
0x1800021ec  movzx   r8d, word ptr [rcx]
0x1800021f0  test    r8w, r8w
0x1800021f4  jz      short loc_18000220B
0x1800021f6  mov     [rax], r8w
0x1800021fa  add     rcx, 2
0x1800021fe  add     rax, 2
0x180002202  dec     r11
0x180002205  sub     rdx, 1
0x180002209  jnz     short loc_1800021E7
0x18000220b  test    rdx, rdx
0x18000220e  lea     rcx, [rax-2]
0x180002212  cmovnz  rcx, rax
0x180002216  mov     [rcx], si
0x180002219  mov     r9d, 2000000h; samDesired
0x18000221f  mov     [rsp+258h+phkResult], rdi; phkResult
0x180002224  xor     r8d, r8d; ulOptions
0x180002227  lea     rdx, [rsp+258h+SubKey]; lpSubKey
0x18000222c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180002233  call    cs:__imp_RegOpenKeyExW
0x180002239  test    eax, 0FFFFFFFCh
0x18000223e  jz      short loc_180002265
0x180002240  mov     rcx, [rsp+258h+var_18]
0x180002248  xor     rcx, rsp; StackCookie
0x18000224b  call    __security_check_cookie
0x180002250  lea     r11, [rsp+258h+var_8]
0x180002258  mov     rbx, [r11+18h]
0x18000225c  mov     rsi, [r11+20h]
0x180002260  mov     rsp, r11
0x180002263  pop     rdi
0x180002264  retn
0x180002265  cmp     eax, 1
0x180002268  jz      short loc_180002240
0x18000226a  lea     r8, [rbx+14h]; unsigned int *
0x18000226e  mov     r9d, 80000000h; unsigned int
0x180002274  lea     rdx, aTrkdebugflags; "TrkDebugFlags"
0x18000227b  mov     rcx, rbx; this
0x18000227e  call    ?Read@CTrkConfiguration@@IEBAXPEBGPEAKK@Z; CTrkConfiguration::Read(ushort const *,ulong *,ulong)
0x180002283  lea     r8, [rbx+18h]; unsigned int *
0x180002287  mov     r9d, 1; unsigned int
0x18000228d  lea     rdx, aDebugstoreflag; "DebugStoreFlags"
0x180002294  mov     rcx, rbx; this
0x180002297  call    ?Read@CTrkConfiguration@@IEBAXPEBGPEAKK@Z; CTrkConfiguration::Read(ushort const *,ulong *,ulong)
0x18000229c  lea     r8, [rbx+10h]; unsigned int *
0x1800022a0  xor     r9d, r9d; unsigned int
0x1800022a3  lea     rdx, aTestflags; "TestFlags"
0x1800022aa  mov     rcx, rbx; this
0x1800022ad  call    ?Read@CTrkConfiguration@@IEBAXPEBGPEAKK@Z; CTrkConfiguration::Read(ushort const *,ulong *,ulong)
0x1800022b2  lea     r8, ?_mtszOperationLog@CTrkConfiguration@@2VCMultiTsz@@A; struct CMultiTsz *
0x1800022b9  mov     rcx, rbx; this
0x1800022bc  lea     rdx, aOperationlogna; "OperationLogName"
0x1800022c3  call    ?Read@CTrkConfiguration@@IEBAXPEBGPEAVCMultiTsz@@0@Z; CTrkConfiguration::Read(ushort const *,CMultiTsz *,ushort const *)
0x1800022c8  jmp     loc_180002240
```
