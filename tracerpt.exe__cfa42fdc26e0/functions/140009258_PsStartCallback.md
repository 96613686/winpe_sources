# PsStartCallback

- ea: `0x140009258`
- end: `0x140009784`
- name: `PsStartCallback`
- size: `1324`
- prototype: `__int64 __fastcall(PEVENT_RECORD Event)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140003a30`

## callees

- `0x140002d98`
- `0x140004c2c`
- `0x140009258`
- `0x140009b40`
- `0x140009c04`
- `0x140009c78`
- `0x14001b7c8`
- `0x14001d700`
- `0x1400400d6`
- `0x140040130`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000931f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140009340`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400093b6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140009738`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000975b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000931f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140009340`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400093b6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140009738`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000975b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140009311`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140009332`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140009357`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400093a8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400093c0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000942b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140009458`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140009519`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140009690`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400096cb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000972a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000974d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140009311`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140009332`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140009357`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400093a8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400093c0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000942b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140009458`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140009519`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140009690`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400096cb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000972a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000974d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000936b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400093d1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140009444`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000947f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000952a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400096a5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400096dd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000936b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400093d1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140009444`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000947f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000952a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400096a5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400096dd`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x1400095db`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x1400095db`

## string_xrefs

- `0x1400092c4`: `ProcessId`
- `0x140009504`: `UserSID`
- `0x140009555`: `UserSID`

## pseudocode

```c
void __fastcall PsStartCallback(PEVENT_RECORD Event)
{
  unsigned int v2; // r12d
  struct _PROCESS_RECORD *ProcessById; // rax
  struct _PROCESS_RECORD *v4; // rdi
  void *v5; // rbx
  HANDLE ProcessHeap; // rax
  void *v7; // rbx
  HANDLE v8; // rax
  HANDLE v9; // rax
  BYTE *v10; // rax
  BYTE *v11; // rsi
  BYTE *v12; // r14
  HANDLE v13; // rax
  unsigned int v14; // ebx
  HANDLE v15; // rax
  BYTE *v16; // rax
  __int64 v17; // r15
  __int64 v18; // rbx
  __int64 v19; // r13
  HANDLE v20; // rax
  LPVOID v21; // rax
  HANDLE v22; // rax
  BYTE *v23; // r8
  unsigned __int16 *v24; // rax
  __int64 v25; // rdx
  __int64 v26; // rcx
  const wchar_t *v27; // r8
  unsigned __int16 *v28; // rcx
  PEVENT_RECORD v29; // r12
  unsigned int v30; // ebx
  HANDLE v31; // rax
  BYTE *v32; // rax
  USHORT Flags; // ax
  BYTE *v34; // rdx
  const wchar_t *v35; // rcx
  __int64 v36; // rdx
  unsigned __int16 *v37; // rax
  unsigned __int16 *v38; // rcx
  HANDLE v39; // rax
  unsigned __int16 *v40; // rax
  HANDLE v41; // rax
  _WORD *v42; // rax
  const wchar_t *v43; // rcx
  __int64 v44; // rdx
  _WORD *v45; // rcx
  HANDLE v46; // rax
  SIZE_T dwBytes; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v48; // [rsp+48h] [rbp-B8h] BYREF
  DWORD cchReferencedDomainName; // [rsp+4Ch] [rbp-B4h] BYREF
  unsigned int v50; // [rsp+50h] [rbp-B0h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+54h] [rbp-ACh] BYREF
  struct _PROCESS_RECORD *v52; // [rsp+58h] [rbp-A8h] BYREF
  PEVENT_RECORD Eventa; // [rsp+60h] [rbp-A0h]
  BYTE Sid[256]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR ReferencedDomainName[64]; // [rsp+170h] [rbp+70h] BYREF
  WCHAR Name[64]; // [rsp+1F0h] [rbp+F0h] BYREF
  unsigned __int16 v57[256]; // [rsp+270h] [rbp+170h] BYREF

  Eventa = Event;
  v48 = 0;
  dwBytes = 0;
  cchReferencedDomainName = 0;
  peUse = 0;
  if ( Event )
  {
    v50 = 4;
    if ( !(unsigned int)GetMofData(Event, L"ProcessId", (BYTE *)&v48, &v50) )
    {
      v2 = v48;
      ProcessById = FindProcessById(v48, 0);
      v52 = ProcessById;
      v4 = ProcessById;
      if ( ProcessById )
      {
        v5 = (void *)*((_QWORD *)ProcessById + 13);
        if ( v5 )
        {
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, v5);
          *((_QWORD *)v4 + 13) = 0;
        }
        v7 = (void *)*((_QWORD *)v4 + 12);
        if ( v7 )
        {
          v8 = GetProcessHeap();
          HeapFree(v8, 0, v7);
          *((_QWORD *)v4 + 12) = 0;
        }
      }
      else
      {
        AddProcess(v2, &v52);
        v4 = v52;
      }
      if ( v4 )
      {
        *((_DWORD *)v4 + 30) = v2;
        v9 = GetProcessHeap();
        v10 = (BYTE *)HeapAlloc(v9, 8u, 0x10u);
        v11 = v10;
        if ( v10 )
        {
          *(_OWORD *)v10 = 0;
          LODWORD(dwBytes) = 16;
          v12 = Sid;
          if ( (unsigned int)GetMofData(Event, L"ImageFileName", v10, (unsigned int *)&dwBytes) != 122 )
            goto LABEL_14;
          v13 = GetProcessHeap();
          HeapFree(v13, 0, v11);
          v14 = dwBytes;
          v15 = GetProcessHeap();
          v16 = (BYTE *)HeapAlloc(v15, 8u, v14);
          v11 = v16;
          if ( !v16 )
            return;
          memset_0(v16, 0, (unsigned int)dwBytes);
          if ( !(unsigned int)GetMofData(Event, L"ImageFileName", v11, (unsigned int *)&dwBytes) )
          {
LABEL_14:
            v17 = -1;
            v18 = -1;
            do
              ++v18;
            while ( v11[v18] );
            HIDWORD(dwBytes) = v18;
            v19 = 2147483646;
            v20 = GetProcessHeap();
            if ( (_DWORD)v18 )
            {
              v21 = HeapAlloc(v20, 8u, 2LL * (unsigned int)(v18 + 1));
              *((_QWORD *)v4 + 13) = v21;
              if ( !v21 )
              {
LABEL_18:
                v22 = GetProcessHeap();
                v23 = v11;
LABEL_63:
                HeapFree(v22, 0, v23);
                return;
              }
              AnsiToUnicode(v11, (unsigned int)(HIDWORD(dwBytes) + 1), v21, (unsigned int)(HIDWORD(dwBytes) + 1));
            }
            else
            {
              v24 = (unsigned __int16 *)HeapAlloc(v20, 8u, 0x800u);
              *((_QWORD *)v4 + 13) = v24;
              if ( !v24 )
                goto LABEL_18;
              v25 = 1024;
              if ( v2 )
              {
                StringCchPrintfW(v24, 0x400u, L"Unknown(0x%08X)", v2);
              }
              else
              {
                v26 = 2147483646;
                v27 = L"Idle";
                do
                {
                  if ( !v26 )
                    break;
                  if ( !*v27 )
                    break;
                  *v24++ = *v27++;
                  --v26;
                  --v25;
                }
                while ( v25 );
                v28 = v24 - 1;
                if ( v25 )
                  v28 = v24;
                *v28 = 0;
              }
            }
            v29 = Eventa;
            LODWORD(dwBytes) = 256;
            if ( (unsigned int)GetMofData(Eventa, L"UserSID", Sid, (unsigned int *)&dwBytes) != 122 )
              goto LABEL_33;
            v30 = dwBytes;
            v31 = GetProcessHeap();
            v32 = (BYTE *)HeapAlloc(v31, 8u, v30);
            v12 = v32;
            if ( !v32 )
              return;
            memset_0(v32, 0, (unsigned int)dwBytes);
            if ( !(unsigned int)GetMofData(v29, L"UserSID", v12, (unsigned int *)&dwBytes) )
            {
LABEL_33:
              if ( (unsigned int)dwBytes <= 4 )
              {
                v34 = v12;
              }
              else
              {
                Flags = v29->EventHeader.Flags;
                if ( (Flags & 0x40) == 0
                  && ((Flags & 0x20) != 0 || (*((_DWORD *)g_TraceContext + 2170) & 0xFFFFFFBF) != 0) )
                {
                  v34 = v12 + 8;
                }
                else
                {
                  v34 = v12 + 16;
                }
              }
              cchReferencedDomainName = 64;
              HIDWORD(dwBytes) = 64;
              if ( LookupAccountSidW(
                     0,
                     v34,
                     Name,
                     (LPDWORD)&dwBytes + 1,
                     ReferencedDomainName,
                     &cchReferencedDomainName,
                     &peUse) )
              {
                v35 = L"\\\\";
                v36 = 256;
                v37 = v57;
                do
                {
                  if ( !v19 )
                    break;
                  if ( !*v35 )
                    break;
                  *v37++ = *v35++;
                  --v19;
                  --v36;
                }
                while ( v36 );
                v38 = v37 - 1;
                if ( v36 )
                  v38 = v37;
                *v38 = 0;
                StringCchCatW(v57, 256, ReferencedDomainName);
                StringCchCatW(v57, 256, L"\\");
                StringCchCatW(v57, 256, Name);
                do
                  ++v17;
                while ( v57[v17] );
                HIDWORD(dwBytes) = v17;
                if ( (_DWORD)v17 )
                {
                  v39 = GetProcessHeap();
                  v40 = (unsigned __int16 *)HeapAlloc(v39, 8u, 2LL * (unsigned int)(v17 + 1));
                  *((_QWORD *)v4 + 12) = v40;
                  if ( v40 )
                    StringCchCopyW(v40, (unsigned int)(HIDWORD(dwBytes) + 1), v57);
                }
              }
              else
              {
                v41 = GetProcessHeap();
                v42 = HeapAlloc(v41, 8u, 0xEu);
                *((_QWORD *)v4 + 12) = v42;
                if ( v42 )
                {
                  v43 = L"system";
                  v44 = 7;
                  do
                  {
                    if ( !v19 )
                      break;
                    if ( !*v43 )
                      break;
                    *v42++ = *v43++;
                    --v19;
                    --v44;
                  }
                  while ( v44 );
                  v45 = v42 - 1;
                  if ( v44 )
                    v45 = v42;
                  *v45 = 0;
                }
              }
            }
          }
          v46 = GetProcessHeap();
          HeapFree(v46, 0, v11);
          if ( v12 && v12 != Sid )
          {
            v22 = GetProcessHeap();
            v23 = v12;
            goto LABEL_63;
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x140009258  push    rbp
0x14000925a  push    rbx
0x14000925b  push    rsi
0x14000925c  push    rdi
0x14000925d  push    r12
0x14000925f  push    r13
0x140009261  push    r14
0x140009263  push    r15
0x140009265  lea     rbp, [rsp-388h]
0x14000926d  sub     rsp, 488h
0x140009274  mov     rax, cs:__security_cookie
0x14000927b  xor     rax, rsp
0x14000927e  mov     [rbp+3C0h+var_50], rax
0x140009285  xor     r13d, r13d
0x140009288  mov     [rsp+4C0h+Event], rcx
0x14000928d  mov     [rsp+4C0h+var_478], r13d
0x140009292  mov     r15, rcx
0x140009295  mov     dword ptr [rsp+4C0h+dwBytes], r13d
0x14000929a  mov     dword ptr [rsp+4C0h+dwBytes+4], r13d
0x14000929f  mov     [rsp+4C0h+var_474], r13d
0x1400092a4  mov     [rsp+4C0h+var_46C], r13d
0x1400092a9  test    rcx, rcx
0x1400092ac  jz      loc_140009761
0x1400092b2  lea     r9, [rsp+4C0h+var_470]; unsigned int *
0x1400092b7  mov     [rsp+4C0h+var_470], 4
0x1400092bf  lea     r8, [rsp+4C0h+var_478]; void *
0x1400092c4  lea     rdx, aProcessid; "ProcessId"
0x1400092cb  call    ?GetMofData@@YAKPEAU_EVENT_RECORD@@PEAGPEAXPEAK@Z; GetMofData(_EVENT_RECORD *,ushort *,void *,ulong *)
0x1400092d0  test    eax, eax
0x1400092d2  jnz     loc_140009761
0x1400092d8  mov     r12d, [rsp+4C0h+var_478]
0x1400092dd  xor     edx, edx; unsigned __int8
0x1400092df  mov     ecx, r12d; unsigned int
0x1400092e2  call    ?FindProcessById@@YAPEAU_PROCESS_RECORD@@KE@Z; FindProcessById(ulong,uchar)
0x1400092e7  mov     [rsp+4C0h+var_468], rax
0x1400092ec  mov     rdi, rax
0x1400092ef  test    rax, rax
0x1400092f2  jnz     short loc_140009308
0x1400092f4  lea     rdx, [rsp+4C0h+var_468]; struct _PROCESS_RECORD **
0x1400092f9  mov     ecx, r12d; unsigned int
0x1400092fc  call    ?AddProcess@@YAEKPEAPEAU_PROCESS_RECORD@@@Z; AddProcess(ulong,_PROCESS_RECORD * *)
0x140009301  mov     rdi, [rsp+4C0h+var_468]
0x140009306  jmp     short loc_14000934A
0x140009308  mov     rbx, [rax+68h]
0x14000930c  test    rbx, rbx
0x14000930f  jz      short loc_140009329
0x140009311  call    cs:__imp_GetProcessHeap
0x140009317  mov     r8, rbx; lpMem
0x14000931a  xor     edx, edx; dwFlags
0x14000931c  mov     rcx, rax; hHeap
0x14000931f  call    cs:__imp_HeapFree
0x140009325  mov     [rdi+68h], r13
0x140009329  mov     rbx, [rdi+60h]
0x14000932d  test    rbx, rbx
0x140009330  jz      short loc_14000934A
0x140009332  call    cs:__imp_GetProcessHeap
0x140009338  mov     r8, rbx; lpMem
0x14000933b  xor     edx, edx; dwFlags
0x14000933d  mov     rcx, rax; hHeap
0x140009340  call    cs:__imp_HeapFree
0x140009346  mov     [rdi+60h], r13
0x14000934a  test    rdi, rdi
0x14000934d  jz      loc_140009761
0x140009353  mov     [rdi+78h], r12d
0x140009357  call    cs:__imp_GetProcessHeap
0x14000935d  mov     ebx, 10h
0x140009362  mov     rcx, rax; hHeap
0x140009365  mov     r8d, ebx; dwBytes
0x140009368  lea     edx, [rbx-8]; dwFlags
0x14000936b  call    cs:__imp_HeapAlloc
0x140009371  mov     rsi, rax
0x140009374  test    rax, rax
0x140009377  jz      loc_140009761
0x14000937d  xorps   xmm0, xmm0
0x140009380  lea     r9, [rsp+4C0h+dwBytes]; unsigned int *
0x140009385  movups  xmmword ptr [rax], xmm0
0x140009388  mov     r8, rax; void *
0x14000938b  mov     dword ptr [rsp+4C0h+dwBytes], ebx
0x14000938f  lea     rdx, aImagefilename; "ImageFileName"
0x140009396  mov     rcx, r15; Event
0x140009399  lea     r14, [rsp+4C0h+Sid]
0x14000939e  call    ?GetMofData@@YAKPEAU_EVENT_RECORD@@PEAGPEAXPEAK@Z; GetMofData(_EVENT_RECORD *,ushort *,void *,ulong *)
0x1400093a3  cmp     eax, 7Ah ; 'z'
0x1400093a6  jnz     short loc_140009411
0x1400093a8  call    cs:__imp_GetProcessHeap
0x1400093ae  mov     r8, rsi; lpMem
0x1400093b1  xor     edx, edx; dwFlags
0x1400093b3  mov     rcx, rax; hHeap
0x1400093b6  call    cs:__imp_HeapFree
0x1400093bc  mov     ebx, dword ptr [rsp+4C0h+dwBytes]
0x1400093c0  call    cs:__imp_GetProcessHeap
0x1400093c6  mov     r8d, ebx; dwBytes
0x1400093c9  mov     edx, 8; dwFlags
0x1400093ce  mov     rcx, rax; hHeap
0x1400093d1  call    cs:__imp_HeapAlloc
0x1400093d7  mov     rsi, rax
0x1400093da  test    rax, rax
0x1400093dd  jz      loc_140009761
0x1400093e3  mov     r8d, dword ptr [rsp+4C0h+dwBytes]; Size
0x1400093e8  xor     edx, edx; Val
0x1400093ea  mov     rcx, rax; void *
0x1400093ed  call    memset_0
0x1400093f2  lea     r9, [rsp+4C0h+dwBytes]; unsigned int *
0x1400093f7  mov     r8, rsi; void *
0x1400093fa  lea     rdx, aImagefilename; "ImageFileName"
0x140009401  mov     rcx, r15; Event
0x140009404  call    ?GetMofData@@YAKPEAU_EVENT_RECORD@@PEAGPEAXPEAK@Z; GetMofData(_EVENT_RECORD *,ushort *,void *,ulong *)
0x140009409  test    eax, eax
0x14000940b  jnz     loc_14000972A
0x140009411  or      r15, 0FFFFFFFFFFFFFFFFh
0x140009415  mov     rbx, r15
0x140009418  inc     rbx
0x14000941b  cmp     [rsi+rbx], r13b
0x14000941f  jnz     short loc_140009418
0x140009421  mov     dword ptr [rsp+4C0h+dwBytes+4], ebx
0x140009425  mov     r13d, 7FFFFFFEh
0x14000942b  call    cs:__imp_GetProcessHeap
0x140009431  mov     edx, 8; dwFlags
0x140009436  mov     rcx, rax; hHeap
0x140009439  test    ebx, ebx
0x14000943b  jz      short loc_140009479
0x14000943d  lea     r8d, [rbx+1]
0x140009441  add     r8, r8; dwBytes
0x140009444  call    cs:__imp_HeapAlloc
0x14000944a  xor     ebx, ebx
0x14000944c  mov     [rdi+68h], rax
0x140009450  mov     r8, rax
0x140009453  test    rax, rax
0x140009456  jnz     short loc_140009466
0x140009458  call    cs:__imp_GetProcessHeap
0x14000945e  mov     r8, rsi
0x140009461  jmp     loc_140009756
0x140009466  mov     edx, dword ptr [rsp+4C0h+dwBytes+4]
0x14000946a  mov     rcx, rsi
0x14000946d  inc     edx
0x14000946f  mov     r9d, edx
0x140009472  call    AnsiToUnicode
0x140009477  jmp     short loc_1400094EA
0x140009479  mov     r8d, 800h; dwBytes
0x14000947f  call    cs:__imp_HeapAlloc
0x140009485  xor     ebx, ebx
0x140009487  mov     [rdi+68h], rax
0x14000948b  test    rax, rax
0x14000948e  jz      short loc_140009458
0x140009490  mov     edx, 400h; unsigned __int64
0x140009495  test    r12d, r12d
0x140009498  jnz     short loc_1400094D8
0x14000949a  mov     rcx, r13
0x14000949d  lea     r8, aIdle; "Idle"
0x1400094a4  test    rcx, rcx
0x1400094a7  jz      short loc_1400094C8
0x1400094a9  movzx   r9d, word ptr [r8]
0x1400094ad  test    r9w, r9w
0x1400094b1  jz      short loc_1400094C8
0x1400094b3  mov     [rax], r9w
0x1400094b7  add     r8, 2
0x1400094bb  add     rax, 2
0x1400094bf  dec     rcx
0x1400094c2  sub     rdx, 1
0x1400094c6  jnz     short loc_1400094A4
0x1400094c8  test    rdx, rdx
0x1400094cb  lea     rcx, [rax-2]
0x1400094cf  cmovnz  rcx, rax
0x1400094d3  mov     [rcx], bx
0x1400094d6  jmp     short loc_1400094EA
0x1400094d8  mov     r9d, r12d
0x1400094db  lea     r8, aUnknown0x08x; "Unknown(0x%08X)"
0x1400094e2  mov     rcx, rax; unsigned __int16 *
0x1400094e5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400094ea  mov     r12, [rsp+4C0h+Event]
0x1400094ef  lea     r9, [rsp+4C0h+dwBytes]; unsigned int *
0x1400094f4  mov     rcx, r12; Event
0x1400094f7  mov     dword ptr [rsp+4C0h+dwBytes], 100h
0x1400094ff  lea     r8, [rsp+4C0h+Sid]; void *
0x140009504  lea     rdx, aUsersid; "UserSID"
0x14000950b  call    ?GetMofData@@YAKPEAU_EVENT_RECORD@@PEAGPEAXPEAK@Z; GetMofData(_EVENT_RECORD *,ushort *,void *,ulong *)
0x140009510  cmp     eax, 7Ah ; 'z'
0x140009513  jnz     short loc_14000956C
0x140009515  mov     ebx, dword ptr [rsp+4C0h+dwBytes]
0x140009519  call    cs:__imp_GetProcessHeap
0x14000951f  mov     r8d, ebx; dwBytes
0x140009522  mov     edx, 8; dwFlags
0x140009527  mov     rcx, rax; hHeap
0x14000952a  call    cs:__imp_HeapAlloc
0x140009530  xor     ebx, ebx
0x140009532  mov     r14, rax
0x140009535  test    rax, rax
0x140009538  jz      loc_140009761
0x14000953e  mov     r8d, dword ptr [rsp+4C0h+dwBytes]; Size
0x140009543  xor     edx, edx; Val
0x140009545  mov     rcx, rax; void *
0x140009548  call    memset_0
0x14000954d  lea     r9, [rsp+4C0h+dwBytes]; unsigned int *
0x140009552  mov     r8, r14; void *
0x140009555  lea     rdx, aUsersid; "UserSID"
0x14000955c  mov     rcx, r12; Event
0x14000955f  call    ?GetMofData@@YAKPEAU_EVENT_RECORD@@PEAGPEAXPEAK@Z; GetMofData(_EVENT_RECORD *,ushort *,void *,ulong *)
0x140009564  test    eax, eax
0x140009566  jnz     loc_14000972A
0x14000956c  cmp     dword ptr [rsp+4C0h+dwBytes], 4
0x140009571  mov     ecx, 40h ; '@'
0x140009576  jbe     short loc_1400095A5
0x140009578  movzx   eax, word ptr [r12+4]
0x14000957e  test    cl, al
0x140009580  jnz     short loc_14000959F
0x140009582  test    al, 20h
0x140009584  jnz     short loc_140009599
0x140009586  mov     rax, cs:?g_TraceContext@@3PEAU_TRACE_CONTEXT_BLOCK@@EA; _TRACE_CONTEXT_BLOCK * g_TraceContext
0x14000958d  test    dword ptr [rax+21E8h], 0FFFFFFBFh
0x140009597  jz      short loc_14000959F
0x140009599  lea     rdx, [r14+8]
0x14000959d  jmp     short loc_1400095A8
0x14000959f  lea     rdx, [r14+10h]
0x1400095a3  jmp     short loc_1400095A8
0x1400095a5  mov     rdx, r14; Sid
0x1400095a8  lea     rax, [rsp+4C0h+var_46C]
0x1400095ad  mov     [rsp+4C0h+var_474], ecx
0x1400095b1  mov     [rsp+4C0h+peUse], rax; peUse
0x1400095b6  lea     r9, [rsp+4C0h+dwBytes+4]; cchName
0x1400095bb  lea     rax, [rsp+4C0h+var_474]
0x1400095c0  mov     dword ptr [rsp+4C0h+dwBytes+4], ecx
0x1400095c4  mov     [rsp+4C0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x1400095c9  lea     r8, [rbp+3C0h+Name]; Name
0x1400095d0  lea     rax, [rbp+3C0h+var_350]
0x1400095d4  xor     ecx, ecx; lpSystemName
0x1400095d6  mov     [rsp+4C0h+ReferencedDomainName], rax; ReferencedDomainName
0x1400095db  call    cs:__imp_LookupAccountSidW
0x1400095e1  test    eax, eax
0x1400095e3  jz      loc_1400096CB
0x1400095e9  mov     r12d, 100h
0x1400095ef  lea     rcx, SubStr; "\\\\"
0x1400095f6  mov     edx, r12d
0x1400095f9  lea     rax, [rbp+3C0h+var_250]
0x140009600  test    r13, r13
0x140009603  jz      short loc_140009624
0x140009605  movzx   r8d, word ptr [rcx]
0x140009609  test    r8w, r8w
0x14000960d  jz      short loc_140009624
0x14000960f  mov     [rax], r8w
0x140009613  add     rcx, 2
0x140009617  add     rax, 2
0x14000961b  dec     r13
0x14000961e  sub     rdx, 1
0x140009622  jnz     short loc_140009600
0x140009624  test    rdx, rdx
0x140009627  lea     rcx, [rax-2]
0x14000962b  lea     r8, [rbp+3C0h+var_350]; unsigned __int16 *
0x14000962f  mov     rdx, r12; unsigned __int64
0x140009632  cmovnz  rcx, rax
0x140009636  mov     [rcx], bx
0x140009639  lea     rcx, [rbp+3C0h+var_250]; unsigned __int16 *
0x140009640  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140009645  lea     r8, asc_140043190; "\\"
0x14000964c  mov     rdx, r12; unsigned __int64
0x14000964f  lea     rcx, [rbp+3C0h+var_250]; unsigned __int16 *
0x140009656  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000965b  lea     r8, [rbp+3C0h+Name]; unsigned __int16 *
0x140009662  mov     rdx, r12; unsigned __int64
0x140009665  lea     rcx, [rbp+3C0h+var_250]; unsigned __int16 *
0x14000966c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140009671  lea     rax, [rbp+3C0h+var_250]
0x140009678  inc     r15
0x14000967b  cmp     [rax+r15*2], bx
0x140009680  jnz     short loc_140009678
0x140009682  mov     dword ptr [rsp+4C0h+dwBytes+4], r15d
0x140009687  test    r15d, r15d
0x14000968a  jz      loc_14000972A
0x140009690  call    cs:__imp_GetProcessHeap
0x140009696  lea     r8d, [r15+1]
0x14000969a  mov     edx, 8; dwFlags
0x14000969f  add     r8, r8; dwBytes
0x1400096a2  mov     rcx, rax; hHeap
0x1400096a5  call    cs:__imp_HeapAlloc
0x1400096ab  mov     [rdi+60h], rax
0x1400096af  test    rax, rax
0x1400096b2  jz      short loc_14000972A
0x1400096b4  mov     edx, dword ptr [rsp+4C0h+dwBytes+4]
0x1400096b8  lea     r8, [rbp+3C0h+var_250]; unsigned __int16 *
0x1400096bf  inc     edx; unsigned __int64
0x1400096c1  mov     rcx, rax; unsigned __int16 *
0x1400096c4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1400096c9  jmp     short loc_14000972A
0x1400096cb  call    cs:__imp_GetProcessHeap
0x1400096d1  mov     edx, 8; dwFlags
0x1400096d6  mov     rcx, rax; hHeap
0x1400096d9  lea     r8d, [rdx+6]; dwBytes
0x1400096dd  call    cs:__imp_HeapAlloc
0x1400096e3  mov     [rdi+60h], rax
0x1400096e7  test    rax, rax
0x1400096ea  jz      short loc_14000972A
0x1400096ec  lea     rcx, aSystem_0; "system"
0x1400096f3  mov     edx, 7
0x1400096f8  test    r13, r13
0x1400096fb  jz      short loc_14000971C
0x1400096fd  movzx   r8d, word ptr [rcx]
0x140009701  test    r8w, r8w
0x140009705  jz      short loc_14000971C
0x140009707  mov     [rax], r8w
0x14000970b  add     rcx, 2
0x14000970f  add     rax, 2
  ... truncated ...
```
