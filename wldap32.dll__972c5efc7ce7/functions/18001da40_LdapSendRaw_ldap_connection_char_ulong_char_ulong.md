# LdapSendRaw(ldap_connection *,char *,ulong,char *,ulong)

- ea: `0x18001da40`
- end: `0x18001ddf3`
- name: `?LdapSendRaw@@YAKPEAUldap_connection@@PEADK1K@Z`
- size: `947`
- prototype: `unsigned int __usercall@<eax>(struct ldap_connection *@<rcx>, char *buf@<rdx>, unsigned int len@<r8d>, char *@<r9>, unsigned int)`
- caller_count: `6`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18000df44`
- `0x18001d470`
- `0x18001ef6c`
- `0x18003d43c`
- `0x18003d78c`
- `0x18003df3c`

## callees

- `0x1800037a8`
- `0x180006510`
- `0x18000cad0`
- `0x18001da40`
- `0x18001e7b0`
- `0x180032bd8`
- `0x180034510`
- `0x180034e6c`
- `0x18004c308`

## import_xrefs

- `WS2_32!__imp_select` at `0x18001db41`
- `WS2_32!__imp_select` at `0x18001dbcd`
- `WS2_32!__imp_select` at `0x18001db41`
- `WS2_32!__imp_select` at `0x18001dbcd`
- `WS2_32!__imp_send` at `0x18001daae`
- `WS2_32!__imp_send` at `0x18001db69`
- `WS2_32!__imp_send` at `0x18001daae`
- `WS2_32!__imp_send` at `0x18001db69`
- `WS2_32!__imp_WSAGetLastError` at `0x18001db81`
- `WS2_32!__imp_WSAGetLastError` at `0x18001dcc8`
- `WS2_32!__imp_WSAGetLastError` at `0x18001dcf8`
- `WS2_32!__imp_WSAGetLastError` at `0x18001db81`
- `WS2_32!__imp_WSAGetLastError` at `0x18001dcc8`
- `WS2_32!__imp_WSAGetLastError` at `0x18001dcf8`

## string_xrefs

- `0x18001dcd7`: `LDAP error during send. sent= 0x%x, length=0x%x, error = 0x%x\n`

## pseudocode

```c
__int64 __fastcall LdapSendRaw(struct ldap_connection *a1, char *buf, unsigned int len, char *a4, unsigned int a5)
{
  unsigned int v8; // ebx
  unsigned int Error; // ebp
  SOCKET v11; // rcx
  bool v12; // zf
  int v13; // r15d
  unsigned int v14; // r12d
  __int64 result; // rax
  SOCKET v16; // rcx
  int TickCount; // r12d
  int v18; // eax
  unsigned int v19; // ecx
  unsigned int v20; // eax
  unsigned int v21; // ebp
  int v22; // r12d
  int v23; // eax
  unsigned int v24; // eax
  int v25; // eax
  __int64 v26; // r8
  char *v27; // rdx
  unsigned int v28; // [rsp+30h] [rbp-288h]
  struct timeval timeout; // [rsp+38h] [rbp-280h] BYREF
  fd_set writefds; // [rsp+50h] [rbp-268h] BYREF

  v8 = 0;
  Error = 0;
  memset_0(&writefds, 0, sizeof(writefds));
  v11 = *((_QWORD *)a1 + 120);
  timeout = (struct timeval)2LL;
  if ( v11 == -1 )
  {
    v13 = *((_DWORD *)a1 + 154);
    v14 = 1000 * v13;
    v28 = 1000 * v13;
    while ( 1 )
    {
      v12 = v8 == len;
      if ( v8 >= len )
        break;
      writefds.fd_array[0] = *((_QWORD *)a1 + 113);
      writefds.fd_count = 1;
      if ( v13 == -1 )
      {
        select(0, 0, &writefds, 0, &timeout);
      }
      else
      {
        if ( v14 < 0x7D0 )
        {
          timeout.tv_sec = 0;
          timeout.tv_usec = 1000 * v14;
        }
        TickCount = LdapGetTickCount();
        select(0, 0, &writefds, 0, &timeout);
        v18 = LdapGetTickCount();
        v19 = v28;
        v20 = v18 - TickCount;
        if ( v20 > v28 )
        {
          v28 = 0;
          v14 = 0;
        }
        else
        {
          v28 -= v20;
          v14 = v19 - v20;
        }
      }
      v16 = *((_QWORD *)a1 + 113);
      *((_BYTE *)a1 + 645) = 1;
      LODWORD(result) = send(v16, &buf[v8], len - v8, 0);
      if ( (_DWORD)result == -1 )
      {
        Error = WSAGetLastError();
        if ( Error != 10035 || v13 != -1 && !v14 )
        {
          v8 = -1;
          v12 = len == -1;
          break;
        }
        v21 = 1000 * *((_DWORD *)a1 + 122);
        if ( v13 != -1 && v21 > v14 )
          v21 = v14;
        v22 = LdapGetTickCount();
        Error = LdapWaitForResponseFromServer(a1, 0, v21, 0, 0, 1);
        v23 = LdapGetTickCount();
        if ( v13 == -1 )
        {
          v14 = v28;
        }
        else
        {
          v24 = v23 - v22;
          if ( v24 <= v28 )
          {
            v14 = v28 - v24;
            v28 -= v24;
          }
          else
          {
            v14 = 0;
            v28 = 0;
          }
        }
        result = 0;
        if ( Error == 81 )
          return result;
      }
      v8 += result;
    }
  }
  else
  {
    *((_BYTE *)a1 + 645) = 1;
    v8 = send(v11, buf, len, 0);
    v12 = v8 == len;
  }
  if ( v12 )
  {
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x800) != 0 )
    {
      LDAPClientPrint(2048, "Data sent on connection 0x%x\n", (_DWORD)a1);
      if ( a4 )
      {
        v26 = a5;
        v27 = a4;
      }
      else
      {
        v26 = v8;
        v27 = buf;
      }
      DumpBuffer(2048, v27, v26);
      LDAPClientTraceEvent(2048, (__int64)"End of send buffer.\n");
    }
  }
  else
  {
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x100000) != 0 )
    {
      v25 = WSAGetLastError();
      LDAPClientPrint(0x100000, "LDAP error during send. sent= 0x%x, length=0x%x, error = 0x%x\n", v8, len, v25);
    }
    if ( v8 == -1 )
    {
      switch ( WSAGetLastError() )
      {
        case 10035:
          Error = 85;
          SetConnectionError(a1, 85);
          break;
        case 10050:
        case 10051:
        case 10052:
        case 10053:
        case 10054:
        case 10057:
        case 10058:
        case 10064:
        case 10065:
          Error = 0;
          break;
        default:
          Error = 82;
          SetConnectionError(a1, 82);
          break;
      }
    }
  }
  return Error;
}

```

## disassembly

```asm
0x18001da40  push    rbx
0x18001da42  push    rbp
0x18001da43  push    rsi
0x18001da44  push    rdi
0x18001da45  push    r12
0x18001da47  push    r13
0x18001da49  push    r14
0x18001da4b  push    r15
0x18001da4d  sub     rsp, 278h
0x18001da54  mov     rax, cs:__security_cookie
0x18001da5b  xor     rax, rsp
0x18001da5e  mov     [rsp+2B8h+var_58], rax
0x18001da66  mov     edi, r8d
0x18001da69  mov     r14, rdx
0x18001da6c  mov     rsi, rcx
0x18001da6f  xor     ebx, ebx
0x18001da71  xor     edx, edx; Val
0x18001da73  lea     rcx, [rsp+2B8h+writefds]; void *
0x18001da78  mov     r8d, 208h; Size
0x18001da7e  mov     ebp, ebx
0x18001da80  mov     r13, r9
0x18001da83  call    memset_0
0x18001da88  mov     rcx, [rsi+3C0h]; s
0x18001da8f  mov     qword ptr [rsp+2B8h+var_280.tv_sec], 2
0x18001da98  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18001da9c  jz      short loc_18001DAC0
0x18001da9e  xor     r9d, r9d; flags
0x18001daa1  mov     byte ptr [rsi+285h], 1
0x18001daa8  mov     r8d, edi; len
0x18001daab  mov     rdx, r14; buf
0x18001daae  call    cs:__imp_send
0x18001dab5  nop     dword ptr [rax+rax+00h]
0x18001daba  mov     ebx, eax
0x18001dabc  cmp     eax, edi
0x18001dabe  jmp     short loc_18001DAD7
0x18001dac0  mov     r15d, [rsi+268h]
0x18001dac7  imul    r12d, r15d, 3E8h
0x18001dace  mov     [rsp+2B8h+var_288], r12d
0x18001dad3  cmp     ebx, edi
0x18001dad5  jb      short loc_18001DB11
0x18001dad7  jnz     loc_18001DCA9
0x18001dadd  cmp     cs:g_fTracingOn, 0
0x18001dae4  jnz     loc_18001DD5C
0x18001daea  mov     eax, ebp
0x18001daec  mov     rcx, [rsp+2B8h+var_58]
0x18001daf4  xor     rcx, rsp; StackCookie
0x18001daf7  call    __security_check_cookie
0x18001dafc  add     rsp, 278h
0x18001db03  pop     r15
0x18001db05  pop     r14
0x18001db07  pop     r13
0x18001db09  pop     r12
0x18001db0b  pop     rdi
0x18001db0c  pop     rsi
0x18001db0d  pop     rbp
0x18001db0e  pop     rbx
0x18001db0f  retn
0x18001db11  mov     rax, [rsi+388h]
0x18001db18  mov     [rsp+2B8h+writefds.fd_array], rax
0x18001db1d  mov     [rsp+2B8h+writefds.fd_count], 1
0x18001db25  cmp     r15d, 0FFFFFFFFh
0x18001db29  jnz     short loc_18001DBA6
0x18001db2b  lea     rax, [rsp+2B8h+var_280]
0x18001db30  xor     r9d, r9d; exceptfds
0x18001db33  lea     r8, [rsp+2B8h+writefds]; writefds
0x18001db38  mov     [rsp+2B8h+timeout], rax; timeout
0x18001db3d  xor     edx, edx; readfds
0x18001db3f  xor     ecx, ecx; nfds
0x18001db41  call    cs:__imp_select
0x18001db48  nop     dword ptr [rax+rax+00h]
0x18001db4d  mov     rcx, [rsi+388h]; s
0x18001db54  mov     r8d, edi
0x18001db57  mov     edx, ebx
0x18001db59  sub     r8d, ebx; len
0x18001db5c  add     rdx, r14; buf
0x18001db5f  mov     byte ptr [rsi+285h], 1
0x18001db66  xor     r9d, r9d; flags
0x18001db69  call    cs:__imp_send
0x18001db70  nop     dword ptr [rax+rax+00h]
0x18001db75  cmp     eax, 0FFFFFFFFh
0x18001db78  jz      short loc_18001DB81
0x18001db7a  add     ebx, eax
0x18001db7c  jmp     loc_18001DAD3
0x18001db81  call    cs:__imp_WSAGetLastError
0x18001db88  nop     dword ptr [rax+rax+00h]
0x18001db8d  mov     ebp, eax
0x18001db8f  cmp     eax, 2733h
0x18001db94  jz      loc_18001DC1A
0x18001db9a  mov     ebx, 0FFFFFFFFh
0x18001db9f  cmp     ebx, edi
0x18001dba1  jmp     loc_18001DAD7
0x18001dba6  cmp     r12d, 7D0h
0x18001dbad  jb      short loc_18001DC05
0x18001dbaf  call    LdapGetTickCount
0x18001dbb4  mov     r12, rax
0x18001dbb7  lea     r8, [rsp+2B8h+writefds]; writefds
0x18001dbbc  lea     rax, [rsp+2B8h+var_280]
0x18001dbc1  xor     r9d, r9d; exceptfds
0x18001dbc4  xor     edx, edx; readfds
0x18001dbc6  mov     [rsp+2B8h+timeout], rax; timeout
0x18001dbcb  xor     ecx, ecx; nfds
0x18001dbcd  call    cs:__imp_select
0x18001dbd4  nop     dword ptr [rax+rax+00h]
0x18001dbd9  call    LdapGetTickCount
0x18001dbde  mov     ecx, [rsp+2B8h+var_288]
0x18001dbe2  sub     eax, r12d
0x18001dbe5  cmp     eax, ecx
0x18001dbe7  ja      short loc_18001DBF7
0x18001dbe9  sub     ecx, eax
0x18001dbeb  mov     [rsp+2B8h+var_288], ecx
0x18001dbef  mov     r12d, ecx
0x18001dbf2  jmp     loc_18001DB4D
0x18001dbf7  xor     ecx, ecx
0x18001dbf9  mov     [rsp+2B8h+var_288], ecx
0x18001dbfd  mov     r12d, ecx
0x18001dc00  jmp     loc_18001DB4D
0x18001dc05  imul    eax, r12d, 3E8h
0x18001dc0c  mov     [rsp+2B8h+var_280.tv_sec], 0
0x18001dc14  mov     [rsp+2B8h+var_280.tv_usec], eax
0x18001dc18  jmp     short loc_18001DBAF
0x18001dc1a  cmp     r15d, 0FFFFFFFFh
0x18001dc1e  jz      short loc_18001DC29
0x18001dc20  test    r12d, r12d
0x18001dc23  jz      loc_18001DB9A
0x18001dc29  imul    ebp, [rsi+1E8h], 3E8h
0x18001dc33  cmp     r15d, 0FFFFFFFFh
0x18001dc37  jz      short loc_18001DC40
0x18001dc39  cmp     ebp, r12d
0x18001dc3c  cmova   ebp, r12d
0x18001dc40  call    LdapGetTickCount
0x18001dc45  xor     r9d, r9d; unsigned int
0x18001dc48  mov     [rsp+2B8h+var_290], 1; char
0x18001dc4d  mov     r8d, ebp; unsigned int
0x18001dc50  mov     [rsp+2B8h+timeout], 0; struct ldapmsg **
0x18001dc59  xor     edx, edx; struct ldap_request *
0x18001dc5b  mov     rcx, rsi; struct ldap_connection *
0x18001dc5e  mov     r12, rax
0x18001dc61  call    ?LdapWaitForResponseFromServer@@YAKPEAUldap_connection@@PEAUldap_request@@KKPEAPEAUldapmsg@@E@Z; LdapWaitForResponseFromServer(ldap_connection *,ldap_request *,ulong,ulong,ldapmsg * *,uchar)
0x18001dc66  mov     ebp, eax
0x18001dc68  call    LdapGetTickCount
0x18001dc6d  cmp     r15d, 0FFFFFFFFh
0x18001dc71  jz      short loc_18001DC94
0x18001dc73  sub     eax, r12d
0x18001dc76  mov     r12d, [rsp+2B8h+var_288]
0x18001dc7b  cmp     eax, r12d
0x18001dc7e  jbe     short loc_18001DC8A
0x18001dc80  xor     r12d, r12d
0x18001dc83  mov     [rsp+2B8h+var_288], r12d
0x18001dc88  jmp     short loc_18001DC99
0x18001dc8a  sub     r12d, eax
0x18001dc8d  mov     [rsp+2B8h+var_288], r12d
0x18001dc92  jmp     short loc_18001DC99
0x18001dc94  mov     r12d, [rsp+2B8h+var_288]
0x18001dc99  xor     eax, eax
0x18001dc9b  cmp     ebp, 51h ; 'Q'
0x18001dc9e  jz      loc_18001DAEC
0x18001dca4  jmp     loc_18001DB7A
0x18001dca9  cmp     cs:g_fTracingOn, 0
0x18001dcb0  jz      short loc_18001DCEF
0x18001dcb2  cmp     cs:g_fProviderEnabled, 0
0x18001dcb9  jz      short loc_18001DCEF
0x18001dcbb  test    cs:g_ulTraceFlags, 100000h
0x18001dcc6  jz      short loc_18001DCEF
0x18001dcc8  call    cs:__imp_WSAGetLastError
0x18001dccf  nop     dword ptr [rax+rax+00h]
0x18001dcd4  mov     r9d, edi
0x18001dcd7  lea     rdx, aLdapErrorDurin; "LDAP error during send. sent= 0x%x, len"...
0x18001dcde  mov     r8d, ebx
0x18001dce1  mov     dword ptr [rsp+2B8h+timeout], eax
0x18001dce5  mov     ecx, 100000h
0x18001dcea  call    LDAPClientPrint
0x18001dcef  cmp     ebx, 0FFFFFFFFh
0x18001dcf2  jnz     loc_18001DAEA
0x18001dcf8  call    cs:__imp_WSAGetLastError
0x18001dcff  nop     dword ptr [rax+rax+00h]
0x18001dd04  add     eax, 0FFFFD8CDh; switch 31 cases
0x18001dd09  cmp     eax, 1Eh
0x18001dd0c  ja      short def_18001DD27; jumptable 000000018001DD27 default case, cases 10036-10049,10055,10056,10059-10063
0x18001dd0e  lea     rdx, __ImageBase
0x18001dd15  movzx   eax, ds:(byte_18001DDD4 - 180000000h)[rdx+rax]
0x18001dd1d  mov     ecx, ds:(jpt_18001DD27 - 180000000h)[rdx+rax*4]
0x18001dd24  add     rcx, rdx
0x18001dd27  jmp     rcx; switch jump
0x18001dd2d  mov     ebp, 55h ; 'U'; jumptable 000000018001DD27 case 10035
0x18001dd32  mov     rcx, rsi
0x18001dd35  mov     edx, ebp
0x18001dd37  call    SetConnectionError
0x18001dd3c  jmp     loc_18001DAEA
0x18001dd41  xor     ebp, ebp; jumptable 000000018001DD27 cases 10050-10054,10057,10058,10064,10065
0x18001dd43  jmp     loc_18001DAEA
0x18001dd48  mov     ebp, 52h ; 'R'; jumptable 000000018001DD27 default case, cases 10036-10049,10055,10056,10059-10063
0x18001dd4d  mov     rcx, rsi
0x18001dd50  mov     edx, ebp
0x18001dd52  call    SetConnectionError
0x18001dd57  jmp     loc_18001DAEA
0x18001dd5c  cmp     cs:g_fProviderEnabled, 0
0x18001dd63  jz      loc_18001DAEA
0x18001dd69  test    cs:g_ulTraceFlags, 800h
0x18001dd74  jz      loc_18001DAEA
0x18001dd7a  mov     r8, rsi
0x18001dd7d  lea     rdx, aDataSentOnConn; "Data sent on connection 0x%x\n"
0x18001dd84  mov     ecx, 800h
0x18001dd89  call    LDAPClientPrint
0x18001dd8e  mov     ecx, 800h
0x18001dd93  test    r13, r13
0x18001dd96  jz      short loc_18001DDA5
0x18001dd98  mov     r8d, [rsp+2B8h+arg_20]
0x18001dda0  mov     rdx, r13
0x18001dda3  jmp     short loc_18001DDAB
0x18001dda5  mov     r8d, ebx
0x18001dda8  mov     rdx, r14
0x18001ddab  call    DumpBuffer
0x18001ddb0  lea     rdx, aEndOfSendBuffe; "End of send buffer.\n"
0x18001ddb7  mov     ecx, 800h
0x18001ddbc  call    LDAPClientTraceEvent
0x18001ddc1  jmp     loc_18001DAEA
```
