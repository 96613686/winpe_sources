# ProtElem::MakeProtElem(wchar_t *,ProtElem * *)

- ea: `0x100421570`
- end: `0x100421bd4`
- name: `?MakeProtElem@ProtElem@@SAKPEA_WPEAPEAV1@@Z`
- size: `1636`
- prototype: `unsigned int __fastcall(wchar_t *, struct ProtElem **)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x100425000`

## callees

- `0x10041f6b0`
- `0x100421400`
- `0x100421570`
- `0x10042b7f0`
- `0x10042b9b0`
- `0x10042c270`
- `0x10042c430`
- `0x1004349f0`
- `0x1004550d0`

## import_xrefs

- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100421657`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100421803`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100421657`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100421803`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100421758`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100421850`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100421a01`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100421a0f`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100421b6d`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100421b83`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100421758`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100421850`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100421a01`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100421a0f`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100421b6d`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100421b83`
- `sqldk!SystemThread_TlsIndex` at `0x1004215f4`
- `sqldk!SystemThread_TlsIndex` at `0x1004217a0`
- `sqldk!SystemThread_TlsOffset` at `0x1004215fd`
- `sqldk!SystemThread_TlsOffset` at `0x1004217a9`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100421618`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004217c4`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100421618`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004217c4`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x100421aed`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x100421aed`

## string_xrefs

- `0x100421594`: `sql\common\dk\sni\include\open.hpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ProtElem::MakeProtElem(wchar_t *a1, struct ProtElem **a2)
{
  __int64 v4; // rbx
  __int64 v5; // rax
  char *v6; // rax
  char *v7; // rsi
  unsigned int v8; // ebx
  const wchar_t *v9; // r9
  __int64 v10; // rbx
  __int64 v11; // rax
  _DWORD *v12; // rax
  _DWORD *v13; // r14
  __int16 v14; // ax
  __int64 v15; // rcx
  __int64 v16; // rbp
  wchar_t v17; // ax
  _OWORD *v18; // rdi
  _OWORD *v19; // rax
  _OWORD *v20; // rdi
  _OWORD *v21; // rax
  __int64 v22; // rbp
  __int64 v24; // [rsp+20h] [rbp-78h]
  __int64 v25; // [rsp+20h] [rbp-78h]
  __int64 v26; // [rsp+28h] [rbp-70h]
  __int64 v27; // [rsp+28h] [rbp-70h]

  if ( (g_XeSniPkg_enabledBitmap & 0x40) != 0 )
    SNIXE_SNI_ENTER_ON(
      "sql\\common\\dk\\sni\\include\\open.hpp",
      "ProtElem::MakeProtElem",
      758,
      L"API|SNIszConnect: '%s', ppProtElem: %p\n",
      a1,
      a2);
  *a2 = 0;
  v4 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v5 = *(_QWORD *)(v4 + 256);
  if ( !v5 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v5 = *(_QWORD *)(v4 + 256);
  }
  v6 = (char *)operator new(
                 0xC24u,
                 *(struct IMemObj **)(*(_QWORD *)(*(_QWORD *)(v5 + 992) + 56LL) + 8LL),
                 1,
                 "sql\\common\\dk\\sni\\include\\open.hpp",
                 764,
                 6u);
  v7 = v6;
  if ( v6 )
  {
    *(_WORD *)v6 = 0;
    *((_WORD *)v6 + 256) = 0;
    *((_WORD *)v6 + 512) = 0;
    *((_WORD *)v6 + 768) = 0;
    *((_WORD *)v6 + 779) = 0;
    *((_WORD *)v6 + 1035) = 0;
    *(_DWORD *)(v6 + 3094) = 257;
    *((_DWORD *)v6 + 775) = -1;
    *((_WORD *)v6 + 1552) = 0;
    v6[3106] = 0;
  }
  else
  {
    v7 = 0;
  }
  if ( !v7 )
  {
    v8 = 14;
    if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
    {
      LODWORD(v26) = 0;
      LODWORD(v24) = 10;
      SNIXE_SNI_ERROR_ON(
        "sql\\common\\dk\\sni\\include\\open.hpp",
        "ProtElem::MakeProtElem",
        769,
        L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
        v24,
        v26,
        14);
    }
    SNISetLastError(10, 14, 50100);
    if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
    {
      LODWORD(v24) = 14;
      SNIXE_SNI_TRACE_ON(
        "sql\\common\\dk\\sni\\include\\open.hpp",
        "ProtElem::MakeProtElem",
        771,
        L"RET|SNI%d{WINERR}\n",
        v24);
    }
    goto LABEL_51;
  }
  v8 = ConnectParameter::ParseConnectionString((ConnectParameter *)v7, a1, 0);
  if ( v8 )
  {
    operator delete(v7, 0xC24u);
    if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
    {
      LODWORD(v24) = v8;
      SNIXE_SNI_TRACE_ON(
        "sql\\common\\dk\\sni\\include\\open.hpp",
        "ProtElem::MakeProtElem",
        784,
        L"RET|SNI%d{WINERR}\n",
        v24);
    }
    goto LABEL_51;
  }
  v10 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v11 = *(_QWORD *)(v10 + 256);
  if ( !v11 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v11 = *(_QWORD *)(v10 + 256);
  }
  v12 = operator new(
          0x810u,
          *(struct IMemObj **)(*(_QWORD *)(*(_QWORD *)(v11 + 992) + 56LL) + 8LL),
          1,
          "sql\\common\\dk\\sni\\include\\open.hpp",
          789,
          6u);
  v13 = v12;
  if ( v12 )
  {
    *v12 = 10;
    v12[1] = 10;
    *((_WORD *)v12 + 4) = 0;
    *((_WORD *)v12 + 260) = 0;
    *((_QWORD *)v12 + 257) = 0;
  }
  else
  {
    v13 = 0;
  }
  if ( !v13 )
  {
    operator delete(v7, 0xC24u);
    v8 = 14;
    if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
    {
      LODWORD(v27) = 0;
      LODWORD(v25) = 10;
      SNIXE_SNI_ERROR_ON(
        "sql\\common\\dk\\sni\\include\\open.hpp",
        "ProtElem::MakeProtElem",
        797,
        L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
        v25,
        v27,
        14);
    }
    SNISetLastError(10, 14, 50100);
    if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
    {
      LODWORD(v25) = 14;
      SNIXE_SNI_TRACE_ON(
        "sql\\common\\dk\\sni\\include\\open.hpp",
        "ProtElem::MakeProtElem",
        799,
        L"RET|SNI%d{WINERR}\n",
        v25);
    }
    goto LABEL_51;
  }
  v8 = ProtElem::Init((ProtElem *)v13, (const wchar_t *const)v7, (const wchar_t *const)v7 + 256);
  if ( !v8 )
  {
    v8 = 87;
    v14 = *((_WORD *)v7 + 768);
    if ( v14 == 110 )
    {
      if ( *((_WORD *)v7 + 769) == 112 && !*((_WORD *)v7 + 770) )
      {
        *v13 = 1;
        v20 = v7 + 1558;
        if ( *((_WORD *)v7 + 779) )
        {
          if ( !wcsncmp((const wchar_t *)v7 + 779, L"\\\\", 2u) )
          {
            v21 = v13 + 258;
            v22 = 4;
            do
            {
              *v21 = *v20;
              v21[1] = v20[1];
              v21[2] = v20[2];
              v21[3] = v20[3];
              v21[4] = v20[4];
              v21[5] = v20[5];
              v21[6] = v20[6];
              v21 += 8;
              *(v21 - 1) = v20[7];
              v20 += 8;
              --v22;
            }
            while ( v22 );
LABEL_49:
            v8 = 0;
            operator delete(v7, 0xC24u);
            *a2 = (struct ProtElem *)v13;
            goto LABEL_41;
          }
        }
      }
    }
    else if ( v14 == 116 )
    {
      v15 = 0;
      v16 = 4;
      while ( 1 )
      {
        v17 = aTcp[v15++];
        if ( v17 != *(_WORD *)&v7[2 * v15 + 1534] )
          break;
        if ( v15 == 4 )
        {
          *v13 = 7;
          *((_WORD *)v13 + 772) = 0;
          *((_BYTE *)v13 + 1546) = 0;
          v13[387] = -1;
          *((_WORD *)v13 + 776) = 0;
          *((_BYTE *)v13 + 1554) = 0;
          if ( !*((_WORD *)v7 + 512) )
          {
            v18 = v7 + 1558;
            if ( *((_WORD *)v7 + 779) )
            {
              if ( (unsigned int)Wcstoi((const wchar_t *)v7 + 779) )
              {
                v19 = v13 + 258;
                do
                {
                  *v19 = *v18;
                  v19[1] = v18[1];
                  v19[2] = v18[2];
                  v19[3] = v18[3];
                  v19[4] = v18[4];
                  v19[5] = v18[5];
                  v19[6] = v18[6];
                  v19 += 8;
                  *(v19 - 1) = v18[7];
                  v18 += 8;
                  --v16;
                }
                while ( v16 );
                goto LABEL_49;
              }
            }
          }
          break;
        }
      }
    }
  }
  operator delete(v7, 0xC24u);
  operator delete(v13, 0x810u);
  if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
  {
    LODWORD(v27) = 25;
    LODWORD(v25) = 10;
    SNIXE_SNI_ERROR_ON(
      "sql\\common\\dk\\sni\\include\\open.hpp",
      "ProtElem::MakeProtElem",
      898,
      L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
      v25,
      v27,
      v8);
  }
  SNISetLastError(10, v8, 50125);
LABEL_41:
  if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
  {
    LODWORD(v25) = v8;
    SNIXE_SNI_TRACE_ON(
      "sql\\common\\dk\\sni\\include\\open.hpp",
      "ProtElem::MakeProtElem",
      901,
      L"RET|SNI%d{WINERR}\n",
      v25);
  }
LABEL_51:
  if ( (g_XeSniPkg_enabledBitmap & 0x80u) != 0 )
    SNIXE_SNI_LEAVE_ON("sql\\common\\dk\\sni\\include\\open.hpp", "ProtElem::MakeProtElem", 758, v9);
  return v8;
}

```

## disassembly

```asm
0x100421570  mov     rax, rsp
0x100421573  push    rbp
0x100421574  push    rsi
0x100421575  push    rdi
0x100421576  push    r12
0x100421578  push    r13
0x10042157a  push    r14
0x10042157c  push    r15
0x10042157e  sub     rsp, 60h
0x100421582  mov     qword ptr [rax-58h], 0FFFFFFFFFFFFFFFEh
0x10042158a  mov     [rax+8], rbx
0x10042158e  mov     r15, rdx
0x100421591  mov     rdi, rcx
0x100421594  lea     r13, aSqlCommonDkSni_7; "sql\\common\\dk\\sni\\include\\open.hpp"
0x10042159b  mov     [rax-50h], r13
0x10042159f  lea     rbp, aProtelemMakepr; "ProtElem::MakeProtElem"
0x1004215a6  mov     [rax-48h], rbp
0x1004215aa  mov     dword ptr [rax-40h], 2F6h
0x1004215b1  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 40h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x1004215b8  jz      short loc_1004215DA
0x1004215ba  mov     [rax-70h], rdx
0x1004215be  mov     [rax-78h], rcx
0x1004215c2  lea     r9, aApiSniszconnec_0; "API|SNIszConnect: '%s', ppProtElem: %p"...
0x1004215c9  mov     r8d, 2F6h; int
0x1004215cf  mov     rdx, rbp; char *
0x1004215d2  mov     rcx, r13; char *
0x1004215d5  call    ?SNIXE_SNI_ENTER_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ENTER_ON(char const *,char const *,int,wchar_t const *,...)
0x1004215da  xor     r12d, r12d
0x1004215dd  mov     [r15], r12
0x1004215e0  mov     [rsp+98h+arg_8], 2FCh
0x1004215eb  mov     rdx, gs:58h
0x1004215f4  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1004215fb  mov     ecx, [rax]
0x1004215fd  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100421604  mov     ebx, [rax]
0x100421606  add     rbx, [rdx+rcx*8]
0x10042160a  mov     rax, [rbx+100h]
0x100421611  test    rax, rax
0x100421614  jnz     short loc_100421625
0x100421616  xor     ecx, ecx
0x100421618  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10042161e  mov     rax, [rbx+100h]
0x100421625  mov     rax, [rax+3E0h]
0x10042162c  mov     rcx, [rax+38h]
0x100421630  mov     rdx, [rcx+8]
0x100421634  mov     [rsp+98h+arg_10], rdx
0x10042163c  mov     byte ptr [rsp+98h+var_70], 6
0x100421641  mov     dword ptr [rsp+98h+var_78], 2FCh
0x100421649  mov     r9, r13
0x10042164c  mov     ecx, 0C24h
0x100421651  mov     r8d, 1
0x100421657  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new(unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x10042165d  mov     rsi, rax
0x100421660  mov     [rsp+98h+arg_18], rax
0x100421668  test    rax, rax
0x10042166b  jz      short loc_1004216BF
0x10042166d  mov     [rax], r12w
0x100421671  mov     [rax+200h], r12w
0x100421679  mov     [rax+400h], r12w
0x100421681  mov     [rax+600h], r12w
0x100421689  mov     [rax+616h], r12w
0x100421691  mov     [rax+816h], r12w
0x100421699  mov     dword ptr [rax+0C16h], 101h
0x1004216a3  mov     dword ptr [rax+0C1Ch], 0FFFFFFFFh
0x1004216ad  mov     word ptr [rax+0C20h], 0
0x1004216b6  mov     byte ptr [rax+0C22h], 0
0x1004216bd  jmp     short loc_1004216C2
0x1004216bf  mov     rsi, r12
0x1004216c2  test    rsi, rsi
0x1004216c5  jnz     short loc_10042173C
0x1004216c7  lea     ebx, [rsi+0Eh]
0x1004216ca  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x1004216d1  jz      short loc_1004216FC
0x1004216d3  mov     [rsp+98h+var_68], ebx
0x1004216d7  mov     dword ptr [rsp+98h+var_70], r12d
0x1004216dc  mov     dword ptr [rsp+98h+var_78], 0Ah
0x1004216e4  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x1004216eb  mov     r8d, 301h; int
0x1004216f1  mov     rdx, rbp; char *
0x1004216f4  mov     rcx, r13; char *
0x1004216f7  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x1004216fc  mov     r8d, 0C3B4h
0x100421702  mov     edx, ebx
0x100421704  mov     ecx, 0Ah
0x100421709  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x10042170e  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100421715  jz      loc_100421BA0
0x10042171b  mov     dword ptr [rsp+98h+var_78], ebx
0x10042171f  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x100421726  mov     r8d, 303h; int
0x10042172c  mov     rdx, rbp; char *
0x10042172f  mov     rcx, r13; char *
0x100421732  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x100421737  jmp     loc_100421BA0
0x10042173c  xor     r8d, r8d; bool
0x10042173f  mov     rdx, rdi; wchar_t *
0x100421742  mov     rcx, rsi; this
0x100421745  call    ?ParseConnectionString@ConnectParameter@@QEAAKPEB_W_N@Z; ConnectParameter::ParseConnectionString(wchar_t const *,bool)
0x10042174a  mov     ebx, eax
0x10042174c  test    eax, eax
0x10042174e  jz      short loc_10042178C
0x100421750  mov     edx, 0C24h
0x100421755  mov     rcx, rsi
0x100421758  call    cs:__imp_??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x10042175e  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100421765  jz      loc_100421BA0
0x10042176b  mov     dword ptr [rsp+98h+var_78], ebx
0x10042176f  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x100421776  mov     r8d, 310h; int
0x10042177c  mov     rdx, rbp; char *
0x10042177f  mov     rcx, r13; char *
0x100421782  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x100421787  jmp     loc_100421BA0
0x10042178c  mov     [rsp+98h+arg_8], 315h
0x100421797  mov     rdx, gs:58h
0x1004217a0  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1004217a7  mov     ecx, [rax]
0x1004217a9  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1004217b0  mov     ebx, [rax]
0x1004217b2  add     rbx, [rdx+rcx*8]
0x1004217b6  mov     rax, [rbx+100h]
0x1004217bd  test    rax, rax
0x1004217c0  jnz     short loc_1004217D1
0x1004217c2  xor     ecx, ecx
0x1004217c4  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1004217ca  mov     rax, [rbx+100h]
0x1004217d1  mov     rax, [rax+3E0h]
0x1004217d8  mov     rcx, [rax+38h]
0x1004217dc  mov     rdx, [rcx+8]
0x1004217e0  mov     [rsp+98h+arg_10], rdx
0x1004217e8  mov     byte ptr [rsp+98h+var_70], 6
0x1004217ed  mov     dword ptr [rsp+98h+var_78], 315h
0x1004217f5  mov     r9, r13
0x1004217f8  mov     ecx, 810h
0x1004217fd  mov     r8d, 1
0x100421803  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new(unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x100421809  mov     r14, rax
0x10042180c  mov     [rsp+98h+arg_18], rax
0x100421814  test    rax, rax
0x100421817  jz      short loc_10042183C
0x100421819  mov     dword ptr [rax], 0Ah
0x10042181f  mov     dword ptr [rax+4], 0Ah
0x100421826  mov     [rax+8], r12w
0x10042182b  mov     [rax+208h], r12w
0x100421833  mov     [rax+808h], r12
0x10042183a  jmp     short loc_10042183F
0x10042183c  mov     r14, r12
0x10042183f  test    r14, r14
0x100421842  jnz     loc_1004218CC
0x100421848  mov     edx, 0C24h
0x10042184d  mov     rcx, rsi
0x100421850  call    cs:__imp_??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x100421856  lea     ebx, [r14+0Eh]
0x10042185a  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100421861  jz      short loc_10042188C
0x100421863  mov     [rsp+98h+var_68], ebx
0x100421867  mov     dword ptr [rsp+98h+var_70], r12d
0x10042186c  mov     dword ptr [rsp+98h+var_78], 0Ah
0x100421874  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x10042187b  mov     r8d, 31Dh; int
0x100421881  mov     rdx, rbp; char *
0x100421884  mov     rcx, r13; char *
0x100421887  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x10042188c  mov     r8d, 0C3B4h
0x100421892  mov     edx, ebx
0x100421894  mov     ecx, 0Ah
0x100421899  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x10042189e  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x1004218a5  jz      loc_100421BA0
0x1004218ab  mov     dword ptr [rsp+98h+var_78], ebx
0x1004218af  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x1004218b6  mov     r8d, 31Fh; int
0x1004218bc  mov     rdx, rbp; char *
0x1004218bf  mov     rcx, r13; char *
0x1004218c2  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x1004218c7  jmp     loc_100421BA0
0x1004218cc  lea     r8, [rsi+200h]; wchar_t *
0x1004218d3  mov     rdx, rsi; wchar_t *
0x1004218d6  mov     rcx, r14; this
0x1004218d9  call    ?Init@ProtElem@@QEAAKQEB_W0@Z; ProtElem::Init(wchar_t const * const,wchar_t const * const)
0x1004218de  mov     ebx, eax
0x1004218e0  test    eax, eax
0x1004218e2  jnz     loc_100421B7B
0x1004218e8  lea     ebx, [rax+57h]
0x1004218eb  movzx   eax, word ptr [rsi+600h]
0x1004218f2  cmp     ax, 6Eh ; 'n'
0x1004218f6  jz      loc_100421A95
0x1004218fc  cmp     ax, 74h ; 't'
0x100421900  jnz     loc_100421B7B
0x100421906  mov     rcx, r12
0x100421909  lea     rdx, aTcp; "tcp"
0x100421910  lea     ebp, [rbx-53h]
0x100421913  nop     dword ptr [rax+00h]
0x100421917  nop     word ptr [rax+rax+00000000h]
0x100421920  movzx   eax, word ptr [rdx+rcx*2]
0x100421924  inc     rcx
0x100421927  cmp     ax, [rsi+rcx*2+5FEh]
0x10042192f  jnz     loc_100421B7B
0x100421935  cmp     rcx, rbp
0x100421938  jnz     short loc_100421920
0x10042193a  mov     dword ptr [r14], 7
0x100421941  mov     word ptr [r14+608h], 0
0x10042194b  mov     byte ptr [r14+60Ah], 0
0x100421953  mov     dword ptr [r14+60Ch], 0FFFFFFFFh
0x10042195e  mov     word ptr [r14+610h], 0
0x100421968  mov     byte ptr [r14+612h], 0
0x100421970  cmp     word ptr [rsi+400h], 0
0x100421978  jnz     loc_100421B7B
0x10042197e  lea     rdi, [rsi+616h]
0x100421985  cmp     word ptr [rdi], 0
0x100421989  jz      short loc_1004219F9
0x10042198b  mov     rcx, rdi; wchar_t *
0x10042198e  call    ?Wcstoi@@YAHPEB_W@Z; Wcstoi(wchar_t const *)
0x100421993  test    eax, eax
0x100421995  jz      loc_100421B7B
0x10042199b  lea     rax, [r14+408h]
0x1004219a2  movups  xmm0, xmmword ptr [rdi]
0x1004219a5  movups  xmmword ptr [rax], xmm0
0x1004219a8  movups  xmm1, xmmword ptr [rdi+10h]
0x1004219ac  movups  xmmword ptr [rax+10h], xmm1
0x1004219b0  movups  xmm0, xmmword ptr [rdi+20h]
0x1004219b4  movups  xmmword ptr [rax+20h], xmm0
0x1004219b8  movups  xmm1, xmmword ptr [rdi+30h]
0x1004219bc  movups  xmmword ptr [rax+30h], xmm1
0x1004219c0  movups  xmm0, xmmword ptr [rdi+40h]
0x1004219c4  movups  xmmword ptr [rax+40h], xmm0
0x1004219c8  movups  xmm1, xmmword ptr [rdi+50h]
0x1004219cc  movups  xmmword ptr [rax+50h], xmm1
0x1004219d0  movups  xmm0, xmmword ptr [rdi+60h]
0x1004219d4  movups  xmmword ptr [rax+60h], xmm0
0x1004219d8  lea     rax, [rax+80h]
0x1004219df  movups  xmm1, xmmword ptr [rdi+70h]
0x1004219e3  movups  xmmword ptr [rax-10h], xmm1
0x1004219e7  lea     rdi, [rdi+80h]
0x1004219ee  sub     rbp, 1
0x1004219f2  jnz     short loc_1004219A2
0x1004219f4  jmp     loc_100421B62
0x1004219f9  mov     edx, 0C24h
0x1004219fe  mov     rcx, rsi
0x100421a01  call    cs:__imp_??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x100421a07  mov     edx, 810h
0x100421a0c  mov     rcx, r14
0x100421a0f  call    cs:__imp_??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x100421a15  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100421a1c  jz      short loc_100421A4E
0x100421a1e  mov     [rsp+98h+var_68], ebx
0x100421a22  mov     dword ptr [rsp+98h+var_70], 19h
0x100421a2a  mov     dword ptr [rsp+98h+var_78], 0Ah
0x100421a32  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x100421a39  mov     r8d, 382h; int
0x100421a3f  lea     rdx, aProtelemMakepr; "ProtElem::MakeProtElem"
0x100421a46  mov     rcx, r13; char *
0x100421a49  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x100421a4e  mov     r8d, 0C3CDh
0x100421a54  mov     edx, ebx
0x100421a56  mov     ecx, 0Ah
0x100421a5b  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x100421a60  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100421a67  jz      loc_100421B99
0x100421a6d  mov     dword ptr [rsp+98h+var_78], ebx
0x100421a71  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x100421a78  mov     r8d, 385h; int
0x100421a7e  lea     rbp, aProtelemMakepr; "ProtElem::MakeProtElem"
0x100421a85  mov     rdx, rbp; char *
0x100421a88  mov     rcx, r13; char *
0x100421a8b  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x100421a90  jmp     loc_100421BA0
0x100421a95  mov     eax, 6Eh ; 'n'
0x100421a9a  cmp     ax, [rsi+600h]
0x100421aa1  jnz     loc_100421B7B
0x100421aa7  mov     eax, 70h ; 'p'
0x100421aac  cmp     ax, [rsi+602h]
0x100421ab3  jnz     loc_100421B7B
0x100421ab9  cmp     r12w, [rsi+604h]
0x100421ac1  jnz     loc_100421B7B
0x100421ac7  mov     dword ptr [r14], 1
0x100421ace  lea     rdi, [rsi+616h]
0x100421ad5  cmp     word ptr [rdi], 0
0x100421ad9  jz      loc_100421B7B
0x100421adf  lea     r8d, [rax-6Eh]; MaxCount
0x100421ae3  lea     rdx, String2; "\\\\"
0x100421aea  mov     rcx, rdi; String1
0x100421aed  call    cs:__imp_wcsncmp
0x100421af3  test    eax, eax
0x100421af5  jnz     loc_100421B7B
0x100421afb  lea     rax, [r14+408h]
0x100421b02  mov     ebp, 4
0x100421b07  nop     word ptr [rax+rax+00000000h]
0x100421b10  movups  xmm0, xmmword ptr [rdi]
0x100421b13  movups  xmmword ptr [rax], xmm0
0x100421b16  movups  xmm1, xmmword ptr [rdi+10h]
0x100421b1a  movups  xmmword ptr [rax+10h], xmm1
0x100421b1e  movups  xmm0, xmmword ptr [rdi+20h]
0x100421b22  movups  xmmword ptr [rax+20h], xmm0
0x100421b26  movups  xmm1, xmmword ptr [rdi+30h]
0x100421b2a  movups  xmmword ptr [rax+30h], xmm1
0x100421b2e  movups  xmm0, xmmword ptr [rdi+40h]
0x100421b32  movups  xmmword ptr [rax+40h], xmm0
0x100421b36  movups  xmm1, xmmword ptr [rdi+50h]
0x100421b3a  movups  xmmword ptr [rax+50h], xmm1
  ... truncated ...
```
