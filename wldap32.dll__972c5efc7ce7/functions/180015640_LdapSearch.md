# LdapSearch

- ea: `0x180015640`
- end: `0x180015bd1`
- name: `LdapSearch`
- size: `1425`
- prototype: `__int64 __fastcall(struct ldap_connection *, int, int, int, unsigned __int16 **, int, char, char, struct ldapcontrolW **, struct ldapcontrolW **, int, int, __int64)`
- caller_count: `10`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x1800153c0`
- `0x1800188d0`
- `0x18001b0d4`
- `0x18001f4a0`
- `0x180028a60`
- `0x18002a4f0`
- `0x18002dd90`
- `0x180048a40`
- `0x180048c10`
- `0x180048d40`

## callees

- `0x1800037a8`
- `0x180006510`
- `0x180008710`
- `0x18000e0d0`
- `0x180014b60`
- `0x180015640`
- `0x180015bd8`
- `0x18001af54`
- `0x18001e8e0`
- `0x180020320`
- `0x1800224cc`
- `0x18002a284`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001587a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001587a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800158a4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015927`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800158a4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015927`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180015b4e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180015b4e`

## string_xrefs

- `0x180015b5a`: `WLDAP32: Process 0x%x is making RootDSE searches which bypass the cache.\n`

## pseudocode

```c
__int64 __fastcall LdapSearch(
        struct ldap_connection *a1,
        int *a2,
        int a3,
        int *a4,
        unsigned __int16 **a5,
        int a6,
        char a7,
        unsigned __int8 a8,
        struct ldapcontrolW **a9,
        struct ldapcontrolW **a10,
        int a11,
        int a12,
        int *a13)
{
  int v13; // eax
  __int64 result; // rax
  __int64 v19; // rdx
  __int64 Request; // rax
  unsigned __int16 *v21; // r8
  unsigned int v22; // r9d
  __int64 v23; // rbx
  int v24; // eax
  const wchar_t *v25; // rcx
  char v26; // dl
  unsigned int v27; // edi
  unsigned __int16 ***v28; // r15
  _WORD *v29; // rax
  unsigned __int16 **v30; // rcx
  unsigned int v31; // eax
  int v32; // ebp
  int v33; // esi
  struct _RTL_CRITICAL_SECTION *v34; // rcx
  unsigned int v35; // eax
  DWORD CurrentProcessId; // eax
  unsigned __int16 *v37; // [rsp+20h] [rbp-68h]
  unsigned int v38; // [rsp+30h] [rbp-58h]
  int v39; // [rsp+50h] [rbp-38h]
  const wchar_t *v40; // [rsp+58h] [rbp-30h]

  v13 = g_fProviderEnabled;
  if ( g_fProviderEnabled && (g_ulTraceFlags & 1) != 0 )
  {
    LDAPSearchLoggingClientTraceEventNoReg((__int64)a1, a3, a4, a2, a5, a7);
    v13 = g_fProviderEnabled;
  }
  if ( g_fTracingOn && v13 && (g_ulTraceFlags & 1) != 0 )
    LDAPClientPrint(
      1,
      "ldap_search called for connection 0x%x: DN is %S. SearchScope is 0x%x. AttributesOnly is 0x%x. Synchronous is 0x%x"
      ". TimeLimit is %lu. SizeLimit is %lu.\n",
      (_DWORD)a1,
      (const wchar_t *)a2,
      a3,
      a6,
      a8,
      a11,
      a12);
  *a13 = -1;
  result = LdapConnect(a1, 0, 0);
  if ( !(_DWORD)result )
  {
    SetConnectionError(a1, 0);
    LOBYTE(v19) = 99;
    Request = LdapCreateRequest(a1, v19);
    v23 = Request;
    if ( Request )
    {
      v24 = *(_DWORD *)(Request + 108);
      v25 = L"ObjectClass=*";
      v26 = a7;
      *(_DWORD *)(v23 + 96) = a11;
      if ( a4 )
        v25 = (const wchar_t *)a4;
      v39 = v24;
      *(_DWORD *)(v23 + 100) = a12;
      v40 = v25;
      *(_BYTE *)(v23 + 187) = a8;
      *(_BYTE *)(v23 + 260) = a7;
      *(_DWORD *)(v23 + 232) = a3;
      *(_DWORD *)(v23 + 256) = a6;
      if ( a9 || (v27 = 0, a10) )
      {
        v35 = LdapCheckControls((struct ldap_request *)v23, a9, a10, a7, 0);
        v27 = v35;
        if ( v35 )
        {
          if ( !g_fTracingOn )
          {
LABEL_62:
            v32 = -1;
            SetConnectionError(a1, v27);
            CloseLdapRequest(v23);
            goto LABEL_26;
          }
          if ( g_fProviderEnabled && (g_ulTraceFlags & 0x8000) != 0 )
            LDAPClientPrint(0x8000, "ldap_search connection 0x%x trouble with SControl, error 0x%x.\n", (_DWORD)a1, v35);
LABEL_58:
          if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x100000) != 0 )
            LDAPClientPrint(0x100000, "ldap_search connection 0x%x send with error of 0x%x.\n", (_DWORD)a1, v27);
          goto LABEL_62;
        }
        v25 = v40;
        v26 = a7;
      }
      if ( (a8 || !*(_BYTE *)(v23 + 185)) && a2 && *(_WORD *)a2 )
      {
        *(_QWORD *)(v23 + 192) = a2;
        v28 = (unsigned __int16 ***)(v23 + 248);
        *(_QWORD *)(v23 + 248) = a5;
        *(_BYTE *)(v23 + 269) = 0;
        *(_QWORD *)(v23 + 240) = v25;
      }
      else
      {
        LOBYTE(v37) = v26;
        v27 = LdapSaveSearchParameters(v23, a2, v25, a5);
        v28 = (unsigned __int16 ***)(v23 + 248);
      }
      if ( !v27 )
      {
        if ( DisableRootDSECache
          || (v29 = *(_WORD **)(v23 + 192)) != 0 && *v29
          || a9
          || a10
          || (v28 = (unsigned __int16 ***)(v23 + 248), (v30 = *(unsigned __int16 ***)(v23 + 248)) == 0)
          || *(_DWORD *)(v23 + 232)
          || *((_BYTE *)a1 + 194)
          || *((_BYTE *)a1 + 195)
          || *((_QWORD *)a1 + 88)
          || !*((_QWORD *)a1 + 52) )
        {
          if ( !*(_QWORD *)(v23 + 192)
            && !*v28
            && !*(_DWORD *)(v23 + 232)
            && g_fTracingOn
            && g_fProviderEnabled
            && (g_ulTraceFlags & 0x10) != 0 )
          {
            CurrentProcessId = GetCurrentProcessId();
            LDAPClientPrint(
              16,
              "WLDAP32: Process 0x%x is making RootDSE searches which bypass the cache.\n",
              CurrentProcessId);
          }
          v31 = SendLdapSearch(
                  (struct ldap_request *)v23,
                  a1,
                  *(unsigned __int16 **)(v23 + 192),
                  *(_DWORD *)(v23 + 232),
                  *(unsigned __int16 **)(v23 + 240),
                  *v28,
                  *(_DWORD *)(v23 + 256),
                  *(_BYTE *)(v23 + 260),
                  (struct CLdapBer **)(v23 + 160),
                  0);
        }
        else
        {
          v31 = AccessLdapCache((struct ldap_request *)v23, a1, v21, v22, v37, v30, v38, *(_BYTE *)(v23 + 260));
        }
        v27 = v31;
        if ( !v31 )
        {
          v32 = v39;
LABEL_26:
          if ( a3 )
          {
            v33 = a3 - 1;
            if ( v33 )
            {
              if ( v33 == 1 )
                _InterlockedIncrement64(&qword_1800660C8);
            }
            else
            {
              _InterlockedIncrement64(&qword_1800660C0);
            }
          }
          else
          {
            _InterlockedIncrement64(&qword_1800660B8);
          }
          EnterCriticalSection((LPCRITICAL_SECTION)(v23 + 48));
          --*(_DWORD *)(v23 + 16);
          if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 4) != 0 )
            LDAPClientPrint(4, "LDAP deref req 0x%x, new count = 0x%x\n", v23, *(_DWORD *)(v23 + 16));
          v34 = (struct _RTL_CRITICAL_SECTION *)(v23 + 48);
          if ( *(_DWORD *)(v23 + 16) )
          {
            LeaveCriticalSection(v34);
          }
          else
          {
            LeaveCriticalSection(v34);
            DereferenceLdapRequest2((__int64 *)v23, 0);
          }
          *a13 = v32;
          return v27;
        }
      }
      goto LABEL_58;
    }
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x4000) != 0 )
      LDAPClientPrint(0x4000, "ldap_search connection 0x%x couldn't allocate request.\n", (_DWORD)a1);
    SetConnectionError(a1, 90);
    return 90;
  }
  return result;
}

```

## disassembly

```asm
0x180015640  mov     [rsp+arg_8], rbp
0x180015645  mov     [rsp+arg_10], rsi
0x18001564a  push    rdi
0x18001564b  push    r12
0x18001564d  push    r13
0x18001564f  push    r14
0x180015651  push    r15
0x180015653  sub     rsp, 60h
0x180015657  mov     eax, cs:g_fProviderEnabled
0x18001565d  mov     rdi, r9
0x180015660  mov     esi, r8d
0x180015663  mov     r15, rdx
0x180015666  mov     r14, rcx
0x180015669  test    eax, eax
0x18001566b  jnz     loc_1800158E9
0x180015671  cmp     cs:g_fTracingOn, 0
0x180015678  mov     ebp, [rsp+88h+arg_58]
0x18001567f  mov     r13d, [rsp+88h+arg_50]
0x180015687  movzx   r12d, [rsp+88h+arg_38]
0x180015690  jnz     loc_1800159D5
0x180015696  mov     rax, [rsp+88h+arg_60]
0x18001569e  xor     r8d, r8d
0x1800156a1  xor     edx, edx
0x1800156a3  mov     rcx, r14
0x1800156a6  mov     dword ptr [rax], 0FFFFFFFFh
0x1800156ac  call    LdapConnect
0x1800156b1  test    eax, eax
0x1800156b3  jnz     loc_1800158CE
0x1800156b9  xor     edx, edx
0x1800156bb  mov     [rsp+88h+arg_0], rbx
0x1800156c3  mov     rcx, r14
0x1800156c6  call    SetConnectionError
0x1800156cb  mov     dl, 63h ; 'c'
0x1800156cd  mov     rcx, r14
0x1800156d0  call    LdapCreateRequest
0x1800156d5  mov     rbx, rax
0x1800156d8  test    rax, rax
0x1800156db  jz      loc_1800159B5
0x1800156e1  mov     eax, [rax+6Ch]
0x1800156e4  lea     rcx, aObjectclass_0; "ObjectClass=*"
0x1800156eb  movzx   edx, [rsp+88h+arg_30]
0x1800156f3  test    rdi, rdi
0x1800156f6  mov     [rbx+60h], r13d
0x1800156fa  mov     r13, [rsp+88h+arg_40]
0x180015702  cmovnz  rcx, rdi
0x180015706  mov     [rsp+88h+var_38], eax
0x18001570a  mov     eax, [rsp+88h+arg_28]
0x180015711  mov     [rbx+64h], ebp
0x180015714  mov     rbp, [rsp+88h+arg_48]
0x18001571c  mov     [rsp+88h+var_30], rcx
0x180015721  mov     [rbx+0BBh], r12b
0x180015728  mov     [rbx+104h], dl
0x18001572e  mov     [rbx+0E8h], esi
0x180015734  mov     [rbx+100h], eax
0x18001573a  test    r13, r13
0x18001573d  jnz     loc_180015A52
0x180015743  xor     edi, edi
0x180015745  test    rbp, rbp
0x180015748  jnz     loc_180015A52
0x18001574e  test    r12b, r12b
0x180015751  jz      loc_180015980
0x180015757  test    r15, r15
0x18001575a  jz      loc_18001598D
0x180015760  cmp     word ptr [r15], 0
0x180015765  jz      loc_18001598D
0x18001576b  mov     rax, [rsp+88h+arg_20]
0x180015773  mov     [rbx+0C0h], r15
0x18001577a  lea     r15, [rbx+0F8h]
0x180015781  mov     [r15], rax
0x180015784  mov     byte ptr [rbx+10Dh], 0
0x18001578b  mov     [rbx+0F0h], rcx
0x180015792  test    edi, edi
0x180015794  jnz     loc_180015AAC
0x18001579a  cmp     cs:DisableRootDSECache, dil
0x1800157a1  jnz     short loc_1800157EA
0x1800157a3  mov     rax, [rbx+0C0h]
0x1800157aa  test    rax, rax
0x1800157ad  jnz     loc_180015935
0x1800157b3  test    r13, r13
0x1800157b6  jnz     short loc_1800157EA
0x1800157b8  test    rbp, rbp
0x1800157bb  jnz     short loc_1800157EA
0x1800157bd  lea     r15, [rbx+0F8h]
0x1800157c4  mov     rcx, [r15]
0x1800157c7  test    rcx, rcx
0x1800157ca  jz      short loc_1800157EA
0x1800157cc  cmp     [rbx+0E8h], ebp
0x1800157d2  jnz     short loc_1800157EA
0x1800157d4  cmp     [r14+0C2h], bpl
0x1800157db  jnz     short loc_1800157EA
0x1800157dd  cmp     [r14+0C3h], bpl
0x1800157e4  jz      loc_180015944
0x1800157ea  cmp     qword ptr [rbx+0C0h], 0
0x1800157f2  jz      loc_180015B10
0x1800157f8  mov     r9d, [rbx+0E8h]; unsigned int
0x1800157ff  lea     rax, [rbx+0A0h]
0x180015806  mov     r8, [rbx+0C0h]; unsigned __int16 *
0x18001580d  mov     rdx, r14; struct ldap_connection *
0x180015810  mov     [rsp+88h+var_40], 0; int
0x180015818  mov     rcx, rbx; struct ldap_request *
0x18001581b  mov     [rsp+88h+var_48], rax; struct CLdapBer **
0x180015820  movzx   eax, byte ptr [rbx+104h]
0x180015827  mov     [rsp+88h+var_50], al; unsigned __int8
0x18001582b  mov     eax, [rbx+100h]
0x180015831  mov     [rsp+88h+var_58], eax; unsigned int
0x180015835  mov     rax, [r15]
0x180015838  mov     [rsp+88h+var_60], rax; unsigned __int16 **
0x18001583d  mov     rax, [rbx+0F0h]
0x180015844  mov     [rsp+88h+var_68], rax; unsigned __int16 *
0x180015849  call    ?SendLdapSearch@@YAKPEAUldap_request@@PEAUldap_connection@@PEAGK2PEAPEAGKEPEAPEAVCLdapBer@@J@Z; SendLdapSearch(ldap_request *,ldap_connection *,ushort *,ulong,ushort *,ushort * *,ulong,uchar,CLdapBer * *,long)
0x18001584e  mov     edi, eax
0x180015850  test    eax, eax
0x180015852  jnz     loc_180015AAC
0x180015858  mov     ebp, [rsp+88h+var_38]
0x18001585c  test    esi, esi
0x18001585e  jz      loc_180015B8D
0x180015864  sub     esi, 1
0x180015867  jz      loc_180015B80
0x18001586d  cmp     esi, 1
0x180015870  jz      loc_180015B73
0x180015876  lea     rcx, [rbx+30h]; lpCriticalSection
0x18001587a  call    cs:__imp_EnterCriticalSection
0x180015881  nop     dword ptr [rax+rax+00h]
0x180015886  dec     dword ptr [rbx+10h]
0x180015889  cmp     cs:g_fTracingOn, 0
0x180015890  jnz     loc_180015B9A
0x180015896  cmp     dword ptr [rbx+10h], 0
0x18001589a  lea     rcx, [rbx+30h]; lpCriticalSection
0x18001589e  jnz     loc_180015927
0x1800158a4  call    cs:__imp_LeaveCriticalSection
0x1800158ab  nop     dword ptr [rax+rax+00h]
0x1800158b0  xor     edx, edx
0x1800158b2  mov     rcx, rbx
0x1800158b5  call    DereferenceLdapRequest2
0x1800158ba  mov     rax, [rsp+88h+arg_60]
0x1800158c2  mov     [rax], ebp
0x1800158c4  mov     eax, edi
0x1800158c6  mov     rbx, [rsp+88h+arg_0]
0x1800158ce  lea     r11, [rsp+88h+var_28]
0x1800158d3  mov     rbp, [r11+38h]
0x1800158d7  mov     rsi, [r11+40h]
0x1800158db  mov     rsp, r11
0x1800158de  pop     r15
0x1800158e0  pop     r14
0x1800158e2  pop     r13
0x1800158e4  pop     r12
0x1800158e6  pop     rdi
0x1800158e7  retn
0x1800158e9  test    byte ptr cs:g_ulTraceFlags, 1
0x1800158f0  jz      loc_180015671
0x1800158f6  movzx   eax, [rsp+88h+arg_30]
0x1800158fe  mov     r9, r15; int
0x180015901  mov     byte ptr [rsp+88h+var_60], al; char
0x180015905  mov     r8, rdi; int
0x180015908  mov     rax, [rsp+88h+arg_20]
0x180015910  mov     edx, esi; int
0x180015912  mov     [rsp+88h+var_68], rax; unsigned __int16 **
0x180015917  call    LDAPSearchLoggingClientTraceEventNoReg
0x18001591c  mov     eax, cs:g_fProviderEnabled
0x180015922  jmp     loc_180015671
0x180015927  call    cs:__imp_LeaveCriticalSection
0x18001592e  nop     dword ptr [rax+rax+00h]
0x180015933  jmp     short loc_1800158BA
0x180015935  cmp     word ptr [rax], 0
0x180015939  jnz     loc_1800157EA
0x18001593f  jmp     loc_1800157B3
0x180015944  cmp     qword ptr [r14+2C0h], 0
0x18001594c  jnz     loc_1800157EA
0x180015952  cmp     qword ptr [r14+1A0h], 0
0x18001595a  jz      loc_1800157EA
0x180015960  movzx   eax, byte ptr [rbx+104h]
0x180015967  mov     rdx, r14; struct ldap_connection *
0x18001596a  mov     [rsp+88h+var_50], al; unsigned __int8
0x18001596e  mov     [rsp+88h+var_60], rcx; unsigned __int16 **
0x180015973  mov     rcx, rbx; struct ldap_request *
0x180015976  call    ?AccessLdapCache@@YAKPEAUldap_request@@PEAUldap_connection@@PEAGK2PEAPEAGKE@Z; AccessLdapCache(ldap_request *,ldap_connection *,ushort *,ulong,ushort *,ushort * *,ulong,uchar)
0x18001597b  jmp     loc_18001584E
0x180015980  cmp     byte ptr [rbx+0B9h], 0
0x180015987  jz      loc_180015757
0x18001598d  mov     r9, [rsp+88h+arg_20]
0x180015995  mov     r8, rcx
0x180015998  mov     byte ptr [rsp+88h+var_68], dl
0x18001599c  mov     rcx, rbx
0x18001599f  mov     rdx, r15
0x1800159a2  call    LdapSaveSearchParameters
0x1800159a7  mov     edi, eax
0x1800159a9  lea     r15, [rbx+0F8h]
0x1800159b0  jmp     loc_180015792
0x1800159b5  cmp     cs:g_fTracingOn, 0
0x1800159bc  jnz     short loc_180015A23
0x1800159be  mov     edx, 5Ah ; 'Z'
0x1800159c3  mov     rcx, r14
0x1800159c6  call    SetConnectionError
0x1800159cb  mov     eax, 5Ah ; 'Z'
0x1800159d0  jmp     loc_1800158C6
0x1800159d5  test    eax, eax
0x1800159d7  jz      loc_180015696
0x1800159dd  test    byte ptr cs:g_ulTraceFlags, 1
0x1800159e4  jz      loc_180015696
0x1800159ea  mov     eax, [rsp+88h+arg_28]
0x1800159f1  lea     rdx, aLdapSearchCall; "ldap_search called for connection 0x%x:"...
0x1800159f8  mov     dword ptr [rsp+88h+var_48], ebp
0x1800159fc  mov     r9, r15
0x1800159ff  mov     dword ptr [rsp+88h+var_50], r13d
0x180015a04  mov     r8, r14
0x180015a07  mov     [rsp+88h+var_58], r12d
0x180015a0c  mov     ecx, 1
0x180015a11  mov     dword ptr [rsp+88h+var_60], eax
0x180015a15  mov     dword ptr [rsp+88h+var_68], esi
0x180015a19  call    LDAPClientPrint
0x180015a1e  jmp     loc_180015696
0x180015a23  cmp     cs:g_fProviderEnabled, 0
0x180015a2a  jz      short loc_1800159BE
0x180015a2c  test    cs:g_ulTraceFlags, 4000h
0x180015a37  jz      short loc_1800159BE
0x180015a39  mov     r8, r14
0x180015a3c  lea     rdx, aLdapSearchConn_1; "ldap_search connection 0x%x couldn't al"...
0x180015a43  mov     ecx, 4000h
0x180015a48  call    LDAPClientPrint
0x180015a4d  jmp     loc_1800159BE
0x180015a52  movzx   r9d, dl; unsigned __int8
0x180015a56  mov     dword ptr [rsp+88h+var_68], 0; unsigned int
0x180015a5e  mov     rdx, r13; struct ldapcontrolW **
0x180015a61  mov     r8, rbp; struct ldapcontrolW **
0x180015a64  mov     rcx, rbx; struct ldap_request *
0x180015a67  call    LdapCheckControls
0x180015a6c  mov     edi, eax
0x180015a6e  test    eax, eax
0x180015a70  jz      loc_180015AFE
0x180015a76  cmp     cs:g_fTracingOn, 0
0x180015a7d  jz      short loc_180015AE2
0x180015a7f  cmp     cs:g_fProviderEnabled, 0
0x180015a86  jz      short loc_180015AAC
0x180015a88  test    cs:g_ulTraceFlags, 8000h
0x180015a93  jz      short loc_180015AAC
0x180015a95  mov     r9d, eax
0x180015a98  lea     rdx, aLdapSearchConn_8; "ldap_search connection 0x%x trouble wit"...
0x180015a9f  mov     r8, r14
0x180015aa2  mov     ecx, 8000h
0x180015aa7  call    LDAPClientPrint
0x180015aac  cmp     cs:g_fTracingOn, 0
0x180015ab3  jz      short loc_180015AE2
0x180015ab5  cmp     cs:g_fProviderEnabled, 0
0x180015abc  jz      short loc_180015AE2
0x180015abe  test    cs:g_ulTraceFlags, 100000h
0x180015ac9  jz      short loc_180015AE2
0x180015acb  mov     r9d, edi
0x180015ace  lea     rdx, aLdapSearchConn_5; "ldap_search connection 0x%x send with e"...
0x180015ad5  mov     r8, r14
0x180015ad8  mov     ecx, 100000h
0x180015add  call    LDAPClientPrint
0x180015ae2  mov     edx, edi
0x180015ae4  mov     rcx, r14
0x180015ae7  mov     ebp, 0FFFFFFFFh
0x180015aec  call    SetConnectionError
0x180015af1  mov     rcx, rbx
0x180015af4  call    CloseLdapRequest
0x180015af9  jmp     loc_18001585C
0x180015afe  mov     rcx, [rsp+88h+var_30]
0x180015b03  movzx   edx, [rsp+88h+arg_30]
0x180015b0b  jmp     loc_18001574E
0x180015b10  cmp     qword ptr [r15], 0
0x180015b14  jnz     loc_1800157F8
0x180015b1a  cmp     dword ptr [rbx+0E8h], 0
0x180015b21  jnz     loc_1800157F8
0x180015b27  cmp     cs:g_fTracingOn, 0
0x180015b2e  jz      loc_1800157F8
0x180015b34  cmp     cs:g_fProviderEnabled, 0
0x180015b3b  jz      loc_1800157F8
0x180015b41  test    byte ptr cs:g_ulTraceFlags, 10h
0x180015b48  jz      loc_1800157F8
0x180015b4e  call    cs:__imp_GetCurrentProcessId
0x180015b55  nop     dword ptr [rax+rax+00h]
0x180015b5a  lea     rdx, aWldap32Process; "WLDAP32: Process 0x%x is making RootDSE"...
0x180015b61  mov     ecx, 10h
0x180015b66  mov     r8d, eax
0x180015b69  call    LDAPClientPrint
0x180015b6e  jmp     loc_1800157F8
0x180015b73  lock inc cs:qword_1800660C8
0x180015b7b  jmp     loc_180015876
0x180015b80  lock inc cs:qword_1800660C0
0x180015b88  jmp     loc_180015876
0x180015b8d  lock inc cs:qword_1800660B8
0x180015b95  jmp     loc_180015876
0x180015b9a  cmp     cs:g_fProviderEnabled, 0
0x180015ba1  jz      loc_180015896
0x180015ba7  test    byte ptr cs:g_ulTraceFlags, 4
0x180015bae  jz      loc_180015896
0x180015bb4  mov     r9d, [rbx+10h]
0x180015bb8  lea     rdx, aLdapDerefReq0x; "LDAP deref req 0x%x, new count = 0x%x\n"
0x180015bbf  mov     r8, rbx
0x180015bc2  mov     ecx, 4
0x180015bc7  call    LDAPClientPrint
0x180015bcc  jmp     loc_180015896
```
