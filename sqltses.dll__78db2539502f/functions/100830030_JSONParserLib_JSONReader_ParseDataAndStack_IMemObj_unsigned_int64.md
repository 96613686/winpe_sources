# JSONParserLib::JSONReader::ParseDataAndStack(IMemObj *,unsigned __int64)

- ea: `0x100830030`
- end: `0x1008303a7`
- name: `?ParseDataAndStack@JSONReader@JSONParserLib@@AEAAKPEAVIMemObj@@_K@Z`
- size: `887`
- prototype: `unsigned int __fastcall(JSONParserLib::JSONReader *__hidden this, struct IMemObj *, unsigned __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x10082fe90`

## callees

- `0x100830030`
- `0x1008303b0`
- `0x100830750`
- `0x100831620`
- `0x100831bd0`

## import_xrefs

- `sqldk!SystemThread_TlsIndex` at `0x1008300a2`
- `sqldk!SystemThread_TlsIndex` at `0x1008300e9`
- `sqldk!SystemThread_TlsOffset` at `0x1008300ab`
- `sqldk!SystemThread_TlsOffset` at `0x1008300f2`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1008300c6`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10083010d`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1008300c6`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10083010d`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x100830305`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x100830339`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x100830305`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x100830339`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x100830311`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x100830345`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x100830311`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x100830345`

## pseudocode

```c
__int64 __fastcall JSONParserLib::JSONReader::ParseDataAndStack(
        JSONParserLib::JSONReader *this,
        struct IMemObj *a2,
        unsigned __int64 a3)
{
  unsigned int v3; // ebx
  unsigned __int64 v4; // rbp
  __int16 v8; // dx
  __int64 v9; // rcx
  __int64 v10; // rbx
  __int64 v11; // rax
  __int64 v12; // rbx
  _QWORD *v13; // r8
  unsigned __int64 v14; // rax
  unsigned __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rax
  bool v18; // zf
  __int64 v19; // rdx
  int v20; // eax
  int **v21; // rdi
  int *v22; // rdi
  unsigned int CurrentToken; // edx
  __int64 v24; // rcx
  __int64 v25; // r8
  int v26; // ecx
  __int64 v27; // rcx
  unsigned int v28; // eax
  __int64 v29; // rdi
  __int64 v30; // r8
  int v31; // eax
  int v32; // eax
  unsigned int v34; // eax
  int v35; // [rsp+20h] [rbp-38h] BYREF
  _QWORD v36[6]; // [rsp+28h] [rbp-30h] BYREF
  unsigned int v37; // [rsp+78h] [rbp+20h] BYREF

  v3 = 0;
  v37 = 0;
  v4 = 0;
  while ( 1 )
  {
    v8 = *(_WORD *)(*((_QWORD *)this + 3) + 2LL * *((unsigned int *)this + 8));
    if ( !v8 )
      break;
    v9 = *((_QWORD *)this + 2);
    if ( !*(_DWORD *)(*(_QWORD *)(v9 + 16) + 28LL) )
      break;
    if ( a3 )
    {
      if ( v4 >= a3 )
      {
        v10 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
        v11 = *(_QWORD *)(v10 + 256);
        if ( !v11 )
        {
          SystemThread::MakeMiniSOSThread(0);
          v11 = *(_QWORD *)(v10 + 256);
        }
        if ( (*(_BYTE *)(v11 + 616) & 0x40) == 0 )
        {
          v12 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
          v13 = *(_QWORD **)(v12 + 256);
          if ( !v13 )
          {
            SystemThread::MakeMiniSOSThread(0);
            v13 = *(_QWORD **)(v12 + 256);
          }
          v14 = __rdtsc();
          v15 = v13[104];
          if ( v14 > v15 || v15 != 0x7FFFFFFFFFFFFFFFLL && v15 - v14 > *(_QWORD *)(v13[76] + 3568LL) )
          {
            v18 = (unsigned int)SOS_Task::Sleep(0, (const struct SOS_WaitInfo *)&yieldWait) == 2;
            goto LABEL_18;
          }
          v16 = v13[75];
          if ( (*(_DWORD *)(v16 + 188) & 4) != 0 )
          {
            v17 = *(_QWORD *)(v16 + 152);
            if ( (*(_BYTE *)(v17 + 616) & 1) == 0 )
            {
              v18 = (*(_DWORD *)(v17 + 800) & 0x180) == 0;
LABEL_18:
              if ( v18 )
                return 7;
            }
          }
        }
        v9 = *((_QWORD *)this + 2);
        v4 = 0;
      }
      ++v4;
    }
    v19 = *(_QWORD *)(v9 + 16);
    v20 = *(_DWORD *)(v19 + 28);
    if ( !v20 )
      return 5;
    v21 = (int **)(*(_QWORD *)(v19 + 16) + 8LL * (unsigned int)(v20 - 1));
    if ( !v21 )
    {
      *_errno() = 22;
      _invalid_parameter_noinfo();
      return 5;
    }
    v22 = *v21;
    v36[0] = v22;
    if ( !v22 )
      return 5;
    CurrentToken = JSONParserLib::JSONReader::GetCurrentToken(this, (enum JSONParserLib::JSON_PARSER_TOKEN *)&v37);
    v3 = CurrentToken;
    if ( CurrentToken || (v24 = *((unsigned int *)this + 8), !*(_WORD *)(*((_QWORD *)this + 3) + 2 * v24)) )
    {
      if ( CurrentToken )
        return v3;
    }
    else
    {
      *((_DWORD *)this + 8) = v24 + 1;
    }
    v25 = v37;
    if ( v37 == 7 || v37 == 10 )
    {
      v22[2] = *((_DWORD *)this + 8) - 1;
      v29 = *((_QWORD *)this + 2);
      v30 = *(_QWORD *)(v29 + 16);
      v31 = *(_DWORD *)(v30 + 28);
      if ( !v31 )
        return 5;
      if ( !(*(_QWORD *)(v30 + 16) + 8LL * (unsigned int)(v31 - 1)) )
      {
        *_errno() = 22;
        _invalid_parameter_noinfo();
        v30 = *(_QWORD *)(v29 + 16);
      }
      v32 = *(_DWORD *)(v30 + 28);
      if ( v32 )
        *(_DWORD *)(v30 + 28) = v32 - 1;
    }
    else
    {
      v26 = *v22;
      if ( v37 == 11 )
      {
        if ( v26 == 1 && !*(_DWORD *)(*((_QWORD *)v22 + 2) + 16LL)
          || v26 == 2 && !*(_DWORD *)(*((_QWORD *)v22 + 2) + 28LL) )
        {
          return 6;
        }
        v3 = JSONParserLib::JSONReader::GetCurrentToken(this, (enum JSONParserLib::JSON_PARSER_TOKEN *)&v37);
        if ( v3 || (v27 = *((unsigned int *)this + 8), !*(_WORD *)(*((_QWORD *)this + 3) + 2 * v27)) )
        {
          if ( v3 )
            return v3;
        }
        else
        {
          *((_DWORD *)this + 8) = v27 + 1;
        }
        v25 = v37;
        if ( v37 == 7 || v37 == 10 )
          return 6;
      }
      else if ( v26 == 1 && *(_DWORD *)(*((_QWORD *)v22 + 2) + 16LL)
             || v26 == 2 && *(_DWORD *)(*((_QWORD *)v22 + 2) + 28LL) )
      {
        return 6;
      }
      if ( *v22 == 1 )
        v28 = JSONParserLib::JSONReader::ParseNameValuePair(this, a2, v25, v36);
      else
        v28 = JSONParserLib::JSONReader::ParseArrayValue(this, a2, v25, v36);
      v3 = v28;
      if ( v28 )
        return v3;
    }
  }
  if ( *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 2) + 16LL) + 28LL) )
    return 6;
  if ( v8 )
  {
    v34 = JSONParserLib::JSONReader::GetCurrentToken(this, (enum JSONParserLib::JSON_PARSER_TOKEN *)&v35);
    v3 = v34;
    if ( !v34 )
    {
      if ( v35 != 12 )
        return 6;
      return v34;
    }
  }
  return v3;
}

```

## disassembly

```asm
0x100830030  mov     [rsp+arg_8], rbx
0x100830035  push    rbp
0x100830036  push    rsi
0x100830037  push    r12
0x100830039  push    r14
0x10083003b  push    r15
0x10083003d  sub     rsp, 30h
0x100830041  xor     ebx, ebx
0x100830043  mov     [rsp+58h+arg_0], rdi
0x100830048  mov     [rsp+58h+arg_18], ebx
0x10083004c  xor     ebp, ebp
0x10083004e  mov     r14, r8
0x100830051  mov     r15, rdx
0x100830054  mov     rsi, rcx
0x100830057  mov     r12, 7FFFFFFFFFFFFFFFh
0x100830061  mov     ecx, [rsi+20h]
0x100830064  mov     rax, [rsi+18h]
0x100830068  movzx   edx, word ptr [rax+rcx*2]
0x10083006c  test    dx, dx
0x10083006f  jz      loc_100830352
0x100830075  mov     rcx, [rsi+10h]
0x100830079  mov     rax, [rcx+10h]
0x10083007d  cmp     dword ptr [rax+1Ch], 0
0x100830081  jbe     loc_100830352
0x100830087  test    r14, r14
0x10083008a  jz      loc_100830194
0x100830090  cmp     rbp, r14
0x100830093  jb      loc_100830191
0x100830099  mov     rdx, gs:58h
0x1008300a2  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1008300a9  mov     ecx, [rax]
0x1008300ab  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1008300b2  mov     ebx, [rax]
0x1008300b4  add     rbx, [rdx+rcx*8]
0x1008300b8  mov     rax, [rbx+100h]
0x1008300bf  test    rax, rax
0x1008300c2  jnz     short loc_1008300D3
0x1008300c4  xor     ecx, ecx
0x1008300c6  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1008300cc  mov     rax, [rbx+100h]
0x1008300d3  test    byte ptr [rax+268h], 40h
0x1008300da  jnz     loc_10083018B
0x1008300e0  mov     rdx, gs:58h
0x1008300e9  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1008300f0  mov     ecx, [rax]
0x1008300f2  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1008300f9  mov     ebx, [rax]
0x1008300fb  add     rbx, [rdx+rcx*8]
0x1008300ff  mov     r8, [rbx+100h]
0x100830106  test    r8, r8
0x100830109  jnz     short loc_10083011A
0x10083010b  xor     ecx, ecx
0x10083010d  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100830113  mov     r8, [rbx+100h]
0x10083011a  rdtsc
0x10083011c  mov     rcx, [r8+340h]
0x100830123  shl     rdx, 20h
0x100830127  or      rax, rdx
0x10083012a  cmp     rax, rcx
0x10083012d  ja      short loc_100830174
0x10083012f  cmp     rcx, r12
0x100830132  jz      short loc_100830147
0x100830134  sub     rcx, rax
0x100830137  mov     rax, [r8+260h]
0x10083013e  cmp     rcx, [rax+0DF0h]
0x100830145  ja      short loc_100830174
0x100830147  mov     rcx, [r8+258h]
0x10083014e  mov     eax, [rcx+0BCh]
0x100830154  test    al, 4
0x100830156  jz      short loc_10083018B
0x100830158  mov     rax, [rcx+98h]
0x10083015f  test    byte ptr [rax+268h], 1
0x100830166  jnz     short loc_10083018B
0x100830168  test    dword ptr [rax+320h], 180h
0x100830172  jmp     short loc_100830185
0x100830174  lea     rdx, ?yieldWait@@3VSOS_WaitInfo@@B; "c@"
0x10083017b  xor     ecx, ecx
0x10083017d  call    ?Sleep@SOS_Task@@SA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@@Z; SOS_Task::Sleep(ulong,SOS_WaitInfo const *)
0x100830182  cmp     eax, 2
0x100830185  jz      loc_100830332
0x10083018b  mov     rcx, [rsi+10h]
0x10083018f  xor     ebp, ebp
0x100830191  inc     rbp
0x100830194  mov     rdx, [rcx+10h]
0x100830198  mov     eax, [rdx+1Ch]
0x10083019b  test    eax, eax
0x10083019d  jz      loc_10083034B
0x1008301a3  lea     ecx, [rax-1]
0x1008301a6  mov     rax, [rdx+10h]
0x1008301aa  lea     rdi, [rax+rcx*8]
0x1008301ae  test    rdi, rdi
0x1008301b1  jz      loc_100830339
0x1008301b7  mov     rdi, [rdi]
0x1008301ba  mov     [rsp+58h+var_30], rdi
0x1008301bf  test    rdi, rdi
0x1008301c2  jz      loc_10083034B
0x1008301c8  lea     rdx, [rsp+58h+arg_18]; enum JSONParserLib::JSON_PARSER_TOKEN *
0x1008301cd  mov     rcx, rsi; this
0x1008301d0  call    ?GetCurrentToken@JSONReader@JSONParserLib@@AEAAKAEAW4JSON_PARSER_TOKEN@2@@Z; JSONParserLib::JSONReader::GetCurrentToken(JSONParserLib::JSON_PARSER_TOKEN &)
0x1008301d5  mov     edx, eax
0x1008301d7  mov     ebx, eax
0x1008301d9  test    eax, eax
0x1008301db  jnz     short loc_1008301F2
0x1008301dd  mov     ecx, [rsi+20h]
0x1008301e0  mov     rax, [rsi+18h]
0x1008301e4  cmp     [rax+rcx*2], bx
0x1008301e8  jz      short loc_1008301F2
0x1008301ea  lea     eax, [rcx+1]
0x1008301ed  mov     [rsi+20h], eax
0x1008301f0  jmp     short loc_1008301FA
0x1008301f2  test    edx, edx
0x1008301f4  jnz     loc_10083038E
0x1008301fa  mov     r8d, [rsp+58h+arg_18]
0x1008301ff  cmp     r8d, 7
0x100830203  jz      loc_1008302DD
0x100830209  cmp     r8d, 0Ah
0x10083020d  jz      loc_1008302DD
0x100830213  mov     ecx, [rdi]
0x100830215  cmp     r8d, 0Bh
0x100830219  jnz     short loc_10083028C
0x10083021b  cmp     ecx, 1
0x10083021e  jnz     short loc_10083022E
0x100830220  mov     rax, [rdi+10h]
0x100830224  cmp     dword ptr [rax+10h], 0
0x100830228  jz      loc_100830360
0x10083022e  cmp     ecx, 2
0x100830231  jnz     short loc_100830241
0x100830233  mov     rax, [rdi+10h]
0x100830237  cmp     dword ptr [rax+1Ch], 0
0x10083023b  jz      loc_100830360
0x100830241  lea     rdx, [rsp+58h+arg_18]; enum JSONParserLib::JSON_PARSER_TOKEN *
0x100830246  mov     rcx, rsi; this
0x100830249  call    ?GetCurrentToken@JSONReader@JSONParserLib@@AEAAKAEAW4JSON_PARSER_TOKEN@2@@Z; JSONParserLib::JSONReader::GetCurrentToken(JSONParserLib::JSON_PARSER_TOKEN &)
0x10083024e  mov     ebx, eax
0x100830250  test    eax, eax
0x100830252  jnz     short loc_100830269
0x100830254  mov     ecx, [rsi+20h]
0x100830257  mov     rax, [rsi+18h]
0x10083025b  cmp     [rax+rcx*2], bx
0x10083025f  jz      short loc_100830269
0x100830261  lea     eax, [rcx+1]
0x100830264  mov     [rsi+20h], eax
0x100830267  jmp     short loc_100830271
0x100830269  test    ebx, ebx
0x10083026b  jnz     loc_10083038E
0x100830271  mov     r8d, [rsp+58h+arg_18]
0x100830276  cmp     r8d, 7
0x10083027a  jz      loc_100830360
0x100830280  cmp     r8d, 0Ah
0x100830284  jz      loc_100830360
0x10083028a  jmp     short loc_1008302B2
0x10083028c  cmp     ecx, 1
0x10083028f  jnz     short loc_10083029F
0x100830291  mov     rax, [rdi+10h]
0x100830295  cmp     dword ptr [rax+10h], 0
0x100830299  jnz     loc_100830360
0x10083029f  cmp     ecx, 2
0x1008302a2  jnz     short loc_1008302B2
0x1008302a4  mov     rax, [rdi+10h]
0x1008302a8  cmp     dword ptr [rax+1Ch], 0
0x1008302ac  jnz     loc_100830360
0x1008302b2  cmp     dword ptr [rdi], 1
0x1008302b5  lea     r9, [rsp+58h+var_30]
0x1008302ba  mov     rdx, r15
0x1008302bd  mov     rcx, rsi
0x1008302c0  jnz     short loc_1008302C9
0x1008302c2  call    ?ParseNameValuePair@JSONReader@JSONParserLib@@AEAAKPEAVIMemObj@@W4JSON_PARSER_TOKEN@2@AEAPEAVJSONNode@2@@Z; JSONParserLib::JSONReader::ParseNameValuePair(IMemObj *,JSONParserLib::JSON_PARSER_TOKEN,JSONParserLib::JSONNode * &)
0x1008302c7  jmp     short loc_1008302CE
0x1008302c9  call    ?ParseArrayValue@JSONReader@JSONParserLib@@AEAAKPEAVIMemObj@@W4JSON_PARSER_TOKEN@2@AEAPEAVJSONNode@2@@Z; JSONParserLib::JSONReader::ParseArrayValue(IMemObj *,JSONParserLib::JSON_PARSER_TOKEN,JSONParserLib::JSONNode * &)
0x1008302ce  mov     ebx, eax
0x1008302d0  test    eax, eax
0x1008302d2  jz      loc_100830061
0x1008302d8  jmp     loc_10083038E
0x1008302dd  mov     eax, [rsi+20h]
0x1008302e0  dec     eax
0x1008302e2  mov     [rdi+8], eax
0x1008302e5  mov     rdi, [rsi+10h]
0x1008302e9  mov     r8, [rdi+10h]
0x1008302ed  mov     eax, [r8+1Ch]
0x1008302f1  test    eax, eax
0x1008302f3  jz      short loc_10083034B
0x1008302f5  lea     ecx, [rax-1]
0x1008302f8  mov     rax, [r8+10h]
0x1008302fc  lea     rdx, [rax+rcx*8]
0x100830300  test    rdx, rdx
0x100830303  jnz     short loc_10083031B
0x100830305  call    cs:__imp__errno
0x10083030b  mov     dword ptr [rax], 16h
0x100830311  call    cs:__imp__invalid_parameter_noinfo
0x100830317  mov     r8, [rdi+10h]
0x10083031b  mov     eax, [r8+1Ch]
0x10083031f  test    eax, eax
0x100830321  jz      loc_100830061
0x100830327  dec     eax
0x100830329  mov     [r8+1Ch], eax
0x10083032d  jmp     loc_100830061
0x100830332  mov     eax, 7
0x100830337  jmp     short loc_100830390
0x100830339  call    cs:__imp__errno
0x10083033f  mov     dword ptr [rax], 16h
0x100830345  call    cs:__imp__invalid_parameter_noinfo
0x10083034b  mov     ebx, 5
0x100830350  jmp     short loc_10083038E
0x100830352  mov     rax, [rsi+10h]
0x100830356  mov     rcx, [rax+10h]
0x10083035a  cmp     dword ptr [rcx+1Ch], 0
0x10083035e  jbe     short loc_100830367
0x100830360  mov     ebx, 6
0x100830365  jmp     short loc_10083038E
0x100830367  test    dx, dx
0x10083036a  jz      short loc_10083038E
0x10083036c  lea     rdx, [rsp+58h+var_38]; enum JSONParserLib::JSON_PARSER_TOKEN *
0x100830371  mov     rcx, rsi; this
0x100830374  call    ?GetCurrentToken@JSONReader@JSONParserLib@@AEAAKAEAW4JSON_PARSER_TOKEN@2@@Z; JSONParserLib::JSONReader::GetCurrentToken(JSONParserLib::JSON_PARSER_TOKEN &)
0x100830379  mov     ebx, eax
0x10083037b  test    eax, eax
0x10083037d  jnz     short loc_10083038E
0x10083037f  cmp     [rsp+58h+var_38], 0Ch
0x100830384  mov     ebx, 6
0x100830389  cmovnz  eax, ebx
0x10083038c  mov     ebx, eax
0x10083038e  mov     eax, ebx
0x100830390  mov     rdi, [rsp+58h+arg_0]
0x100830395  mov     rbx, [rsp+58h+arg_8]
0x10083039a  add     rsp, 30h
0x10083039e  pop     r15
0x1008303a0  pop     r14
0x1008303a2  pop     r12
0x1008303a4  pop     rsi
0x1008303a5  pop     rbp
0x1008303a6  retn
```
