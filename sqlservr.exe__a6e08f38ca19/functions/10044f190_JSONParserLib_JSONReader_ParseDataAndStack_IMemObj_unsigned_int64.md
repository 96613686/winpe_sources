# JSONParserLib::JSONReader::ParseDataAndStack(IMemObj *,unsigned __int64)

- ea: `0x10044f190`
- end: `0x10044f507`
- name: `?ParseDataAndStack@JSONReader@JSONParserLib@@AEAAKPEAVIMemObj@@_K@Z`
- size: `887`
- prototype: `unsigned int __fastcall(JSONParserLib::JSONReader *__hidden this, struct IMemObj *, unsigned __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x10044eff0`

## callees

- `0x1004095e0`
- `0x10044f190`
- `0x10044f510`
- `0x10044f8b0`
- `0x100450780`

## import_xrefs

- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10044f226`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10044f26d`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10044f226`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10044f26d`
- `sqldk!SystemThread_TlsOffset` at `0x10044f20b`
- `sqldk!SystemThread_TlsOffset` at `0x10044f252`
- `sqldk!SystemThread_TlsIndex` at `0x10044f202`
- `sqldk!SystemThread_TlsIndex` at `0x10044f249`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x10044f465`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x10044f499`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x10044f465`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x10044f499`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x10044f471`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x10044f4a5`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x10044f471`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x10044f4a5`

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
0x10044f190  mov     [rsp+arg_8], rbx
0x10044f195  push    rbp
0x10044f196  push    rsi
0x10044f197  push    r12
0x10044f199  push    r14
0x10044f19b  push    r15
0x10044f19d  sub     rsp, 30h
0x10044f1a1  xor     ebx, ebx
0x10044f1a3  mov     [rsp+58h+arg_0], rdi
0x10044f1a8  mov     [rsp+58h+arg_18], ebx
0x10044f1ac  xor     ebp, ebp
0x10044f1ae  mov     r14, r8
0x10044f1b1  mov     r15, rdx
0x10044f1b4  mov     rsi, rcx
0x10044f1b7  mov     r12, 7FFFFFFFFFFFFFFFh
0x10044f1c1  mov     ecx, [rsi+20h]
0x10044f1c4  mov     rax, [rsi+18h]
0x10044f1c8  movzx   edx, word ptr [rax+rcx*2]
0x10044f1cc  test    dx, dx
0x10044f1cf  jz      loc_10044F4B2
0x10044f1d5  mov     rcx, [rsi+10h]
0x10044f1d9  mov     rax, [rcx+10h]
0x10044f1dd  cmp     dword ptr [rax+1Ch], 0
0x10044f1e1  jbe     loc_10044F4B2
0x10044f1e7  test    r14, r14
0x10044f1ea  jz      loc_10044F2F4
0x10044f1f0  cmp     rbp, r14
0x10044f1f3  jb      loc_10044F2F1
0x10044f1f9  mov     rdx, gs:58h
0x10044f202  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10044f209  mov     ecx, [rax]
0x10044f20b  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10044f212  mov     ebx, [rax]
0x10044f214  add     rbx, [rdx+rcx*8]
0x10044f218  mov     rax, [rbx+100h]
0x10044f21f  test    rax, rax
0x10044f222  jnz     short loc_10044F233
0x10044f224  xor     ecx, ecx
0x10044f226  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10044f22c  mov     rax, [rbx+100h]
0x10044f233  test    byte ptr [rax+268h], 40h
0x10044f23a  jnz     loc_10044F2EB
0x10044f240  mov     rdx, gs:58h
0x10044f249  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10044f250  mov     ecx, [rax]
0x10044f252  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10044f259  mov     ebx, [rax]
0x10044f25b  add     rbx, [rdx+rcx*8]
0x10044f25f  mov     r8, [rbx+100h]
0x10044f266  test    r8, r8
0x10044f269  jnz     short loc_10044F27A
0x10044f26b  xor     ecx, ecx
0x10044f26d  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10044f273  mov     r8, [rbx+100h]
0x10044f27a  rdtsc
0x10044f27c  mov     rcx, [r8+340h]
0x10044f283  shl     rdx, 20h
0x10044f287  or      rax, rdx
0x10044f28a  cmp     rax, rcx
0x10044f28d  ja      short loc_10044F2D4
0x10044f28f  cmp     rcx, r12
0x10044f292  jz      short loc_10044F2A7
0x10044f294  sub     rcx, rax
0x10044f297  mov     rax, [r8+260h]
0x10044f29e  cmp     rcx, [rax+0DF0h]
0x10044f2a5  ja      short loc_10044F2D4
0x10044f2a7  mov     rcx, [r8+258h]
0x10044f2ae  mov     eax, [rcx+0BCh]
0x10044f2b4  test    al, 4
0x10044f2b6  jz      short loc_10044F2EB
0x10044f2b8  mov     rax, [rcx+98h]
0x10044f2bf  test    byte ptr [rax+268h], 1
0x10044f2c6  jnz     short loc_10044F2EB
0x10044f2c8  test    dword ptr [rax+320h], 180h
0x10044f2d2  jmp     short loc_10044F2E5
0x10044f2d4  lea     rdx, ?yieldWait@@3VSOS_WaitInfo@@B; "c@"
0x10044f2db  xor     ecx, ecx
0x10044f2dd  call    ?Sleep@SOS_Task@@SA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@@Z; SOS_Task::Sleep(ulong,SOS_WaitInfo const *)
0x10044f2e2  cmp     eax, 2
0x10044f2e5  jz      loc_10044F492
0x10044f2eb  mov     rcx, [rsi+10h]
0x10044f2ef  xor     ebp, ebp
0x10044f2f1  inc     rbp
0x10044f2f4  mov     rdx, [rcx+10h]
0x10044f2f8  mov     eax, [rdx+1Ch]
0x10044f2fb  test    eax, eax
0x10044f2fd  jz      loc_10044F4AB
0x10044f303  lea     ecx, [rax-1]
0x10044f306  mov     rax, [rdx+10h]
0x10044f30a  lea     rdi, [rax+rcx*8]
0x10044f30e  test    rdi, rdi
0x10044f311  jz      loc_10044F499
0x10044f317  mov     rdi, [rdi]
0x10044f31a  mov     [rsp+58h+var_30], rdi
0x10044f31f  test    rdi, rdi
0x10044f322  jz      loc_10044F4AB
0x10044f328  lea     rdx, [rsp+58h+arg_18]; enum JSONParserLib::JSON_PARSER_TOKEN *
0x10044f32d  mov     rcx, rsi; this
0x10044f330  call    ?GetCurrentToken@JSONReader@JSONParserLib@@AEAAKAEAW4JSON_PARSER_TOKEN@2@@Z; JSONParserLib::JSONReader::GetCurrentToken(JSONParserLib::JSON_PARSER_TOKEN &)
0x10044f335  mov     edx, eax
0x10044f337  mov     ebx, eax
0x10044f339  test    eax, eax
0x10044f33b  jnz     short loc_10044F352
0x10044f33d  mov     ecx, [rsi+20h]
0x10044f340  mov     rax, [rsi+18h]
0x10044f344  cmp     [rax+rcx*2], bx
0x10044f348  jz      short loc_10044F352
0x10044f34a  lea     eax, [rcx+1]
0x10044f34d  mov     [rsi+20h], eax
0x10044f350  jmp     short loc_10044F35A
0x10044f352  test    edx, edx
0x10044f354  jnz     loc_10044F4EE
0x10044f35a  mov     r8d, [rsp+58h+arg_18]
0x10044f35f  cmp     r8d, 7
0x10044f363  jz      loc_10044F43D
0x10044f369  cmp     r8d, 0Ah
0x10044f36d  jz      loc_10044F43D
0x10044f373  mov     ecx, [rdi]
0x10044f375  cmp     r8d, 0Bh
0x10044f379  jnz     short loc_10044F3EC
0x10044f37b  cmp     ecx, 1
0x10044f37e  jnz     short loc_10044F38E
0x10044f380  mov     rax, [rdi+10h]
0x10044f384  cmp     dword ptr [rax+10h], 0
0x10044f388  jz      loc_10044F4C0
0x10044f38e  cmp     ecx, 2
0x10044f391  jnz     short loc_10044F3A1
0x10044f393  mov     rax, [rdi+10h]
0x10044f397  cmp     dword ptr [rax+1Ch], 0
0x10044f39b  jz      loc_10044F4C0
0x10044f3a1  lea     rdx, [rsp+58h+arg_18]; enum JSONParserLib::JSON_PARSER_TOKEN *
0x10044f3a6  mov     rcx, rsi; this
0x10044f3a9  call    ?GetCurrentToken@JSONReader@JSONParserLib@@AEAAKAEAW4JSON_PARSER_TOKEN@2@@Z; JSONParserLib::JSONReader::GetCurrentToken(JSONParserLib::JSON_PARSER_TOKEN &)
0x10044f3ae  mov     ebx, eax
0x10044f3b0  test    eax, eax
0x10044f3b2  jnz     short loc_10044F3C9
0x10044f3b4  mov     ecx, [rsi+20h]
0x10044f3b7  mov     rax, [rsi+18h]
0x10044f3bb  cmp     [rax+rcx*2], bx
0x10044f3bf  jz      short loc_10044F3C9
0x10044f3c1  lea     eax, [rcx+1]
0x10044f3c4  mov     [rsi+20h], eax
0x10044f3c7  jmp     short loc_10044F3D1
0x10044f3c9  test    ebx, ebx
0x10044f3cb  jnz     loc_10044F4EE
0x10044f3d1  mov     r8d, [rsp+58h+arg_18]
0x10044f3d6  cmp     r8d, 7
0x10044f3da  jz      loc_10044F4C0
0x10044f3e0  cmp     r8d, 0Ah
0x10044f3e4  jz      loc_10044F4C0
0x10044f3ea  jmp     short loc_10044F412
0x10044f3ec  cmp     ecx, 1
0x10044f3ef  jnz     short loc_10044F3FF
0x10044f3f1  mov     rax, [rdi+10h]
0x10044f3f5  cmp     dword ptr [rax+10h], 0
0x10044f3f9  jnz     loc_10044F4C0
0x10044f3ff  cmp     ecx, 2
0x10044f402  jnz     short loc_10044F412
0x10044f404  mov     rax, [rdi+10h]
0x10044f408  cmp     dword ptr [rax+1Ch], 0
0x10044f40c  jnz     loc_10044F4C0
0x10044f412  cmp     dword ptr [rdi], 1
0x10044f415  lea     r9, [rsp+58h+var_30]
0x10044f41a  mov     rdx, r15
0x10044f41d  mov     rcx, rsi
0x10044f420  jnz     short loc_10044F429
0x10044f422  call    ?ParseNameValuePair@JSONReader@JSONParserLib@@AEAAKPEAVIMemObj@@W4JSON_PARSER_TOKEN@2@AEAPEAVJSONNode@2@@Z; JSONParserLib::JSONReader::ParseNameValuePair(IMemObj *,JSONParserLib::JSON_PARSER_TOKEN,JSONParserLib::JSONNode * &)
0x10044f427  jmp     short loc_10044F42E
0x10044f429  call    ?ParseArrayValue@JSONReader@JSONParserLib@@AEAAKPEAVIMemObj@@W4JSON_PARSER_TOKEN@2@AEAPEAVJSONNode@2@@Z; JSONParserLib::JSONReader::ParseArrayValue(IMemObj *,JSONParserLib::JSON_PARSER_TOKEN,JSONParserLib::JSONNode * &)
0x10044f42e  mov     ebx, eax
0x10044f430  test    eax, eax
0x10044f432  jz      loc_10044F1C1
0x10044f438  jmp     loc_10044F4EE
0x10044f43d  mov     eax, [rsi+20h]
0x10044f440  dec     eax
0x10044f442  mov     [rdi+8], eax
0x10044f445  mov     rdi, [rsi+10h]
0x10044f449  mov     r8, [rdi+10h]
0x10044f44d  mov     eax, [r8+1Ch]
0x10044f451  test    eax, eax
0x10044f453  jz      short loc_10044F4AB
0x10044f455  lea     ecx, [rax-1]
0x10044f458  mov     rax, [r8+10h]
0x10044f45c  lea     rdx, [rax+rcx*8]
0x10044f460  test    rdx, rdx
0x10044f463  jnz     short loc_10044F47B
0x10044f465  call    cs:__imp__errno
0x10044f46b  mov     dword ptr [rax], 16h
0x10044f471  call    cs:__imp__invalid_parameter_noinfo
0x10044f477  mov     r8, [rdi+10h]
0x10044f47b  mov     eax, [r8+1Ch]
0x10044f47f  test    eax, eax
0x10044f481  jz      loc_10044F1C1
0x10044f487  dec     eax
0x10044f489  mov     [r8+1Ch], eax
0x10044f48d  jmp     loc_10044F1C1
0x10044f492  mov     eax, 7
0x10044f497  jmp     short loc_10044F4F0
0x10044f499  call    cs:__imp__errno
0x10044f49f  mov     dword ptr [rax], 16h
0x10044f4a5  call    cs:__imp__invalid_parameter_noinfo
0x10044f4ab  mov     ebx, 5
0x10044f4b0  jmp     short loc_10044F4EE
0x10044f4b2  mov     rax, [rsi+10h]
0x10044f4b6  mov     rcx, [rax+10h]
0x10044f4ba  cmp     dword ptr [rcx+1Ch], 0
0x10044f4be  jbe     short loc_10044F4C7
0x10044f4c0  mov     ebx, 6
0x10044f4c5  jmp     short loc_10044F4EE
0x10044f4c7  test    dx, dx
0x10044f4ca  jz      short loc_10044F4EE
0x10044f4cc  lea     rdx, [rsp+58h+var_38]; enum JSONParserLib::JSON_PARSER_TOKEN *
0x10044f4d1  mov     rcx, rsi; this
0x10044f4d4  call    ?GetCurrentToken@JSONReader@JSONParserLib@@AEAAKAEAW4JSON_PARSER_TOKEN@2@@Z; JSONParserLib::JSONReader::GetCurrentToken(JSONParserLib::JSON_PARSER_TOKEN &)
0x10044f4d9  mov     ebx, eax
0x10044f4db  test    eax, eax
0x10044f4dd  jnz     short loc_10044F4EE
0x10044f4df  cmp     [rsp+58h+var_38], 0Ch
0x10044f4e4  mov     ebx, 6
0x10044f4e9  cmovnz  eax, ebx
0x10044f4ec  mov     ebx, eax
0x10044f4ee  mov     eax, ebx
0x10044f4f0  mov     rdi, [rsp+58h+arg_0]
0x10044f4f5  mov     rbx, [rsp+58h+arg_8]
0x10044f4fa  add     rsp, 30h
0x10044f4fe  pop     r15
0x10044f500  pop     r14
0x10044f502  pop     r12
0x10044f504  pop     rsi
0x10044f505  pop     rbp
0x10044f506  retn
```
