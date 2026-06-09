# WinSAT::GraphicsOp::AssessmentThread(void)

- ea: `0x140079e98`
- end: `0x14007a4c8`
- name: `?AssessmentThread@GraphicsOp@WinSAT@@AEAAIXZ`
- size: `1584`
- prototype: `__int64 __fastcall(WinSAT::GraphicsOp *this)`
- caller_count: `1`
- callee_count: `24`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14007a4d0`

## callees

- `0x140001abc`
- `0x140003611`
- `0x140004348`
- `0x140005f10`
- `0x140005f4c`
- `0x1400085b4`
- `0x140016d04`
- `0x140017af0`
- `0x14001854c`
- `0x14001f940`
- `0x14003ec14`
- `0x1400478c0`
- `0x14004fe00`
- `0x140079e98`
- `0x14007fa4c`
- `0x140081118`
- `0x1400816c0`
- `0x140081d4c`
- `0x140081ec8`
- `0x140082680`
- `0x1400852f0`
- `0x140086a74`
- `0x140113220`
- `0x14011a010`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x14007a12d`
- `KERNEL32!GetTickCount` at `0x14007a1d8`
- `KERNEL32!GetTickCount` at `0x14007a12d`
- `KERNEL32!GetTickCount` at `0x14007a1d8`
- `KERNEL32!DeleteFileW` at `0x14007a45b`
- `KERNEL32!DeleteFileW` at `0x14007a45b`
- `KERNEL32!GetThreadPriority` at `0x140079ed5`
- `KERNEL32!GetThreadPriority` at `0x140079ed5`
- `KERNEL32!GetCurrentThread` at `0x140079ecc`
- `KERNEL32!GetCurrentThread` at `0x140079ecc`
- `KERNEL32!SetEvent` at `0x14007a480`
- `KERNEL32!SetEvent` at `0x14007a480`
- `KERNEL32!CopyFileW` at `0x14007a44c`
- `KERNEL32!CopyFileW` at `0x14007a44c`

## string_xrefs

- `0x140079ede`: `GraphicsOp::AssessmentThread Launched with priority %d`

## pseudocode

```c
__int64 __fastcall WinSAT::GraphicsOp::AssessmentThread(WinSAT::GraphicsOp *this)
{
  HANDLE CurrentThread; // rax
  int ThreadPriority; // eax
  char *v4; // r12
  char v5; // r15
  __int64 v6; // r9
  enum D3DCommon::tag_EVideoDriverModel *v7; // rdx
  __int64 v8; // r9
  int PrimaryAdapterDriverModel; // esi
  char v10; // r14
  D3DCommon *v11; // rcx
  const unsigned __int16 *v12; // rdx
  unsigned __int16 v13; // dx
  __int64 v14; // rax
  __int64 *v15; // r12
  unsigned __int16 v16; // r9
  const unsigned __int16 *v17; // rax
  __int64 *v18; // rax
  __int64 v19; // rsi
  unsigned __int16 v20; // r9
  const unsigned __int16 *v21; // rax
  __int64 *v22; // rax
  D3DCommon *v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // r8
  int started; // eax
  int v27; // eax
  __int64 v28; // rax
  __int64 *v29; // r12
  unsigned __int16 v30; // r9
  const unsigned __int16 *v31; // rax
  __int64 *v32; // rax
  char v33; // si
  __int64 v34; // rax
  const wchar_t *v35; // rsi
  const unsigned __int16 *v36; // r14
  int v37; // ecx
  __int64 v38; // rax
  char *v39; // rcx
  __int64 result; // rax
  char v41; // [rsp+31h] [rbp-287h]
  __int64 v42; // [rsp+38h] [rbp-280h] BYREF
  __int64 v43[2]; // [rsp+40h] [rbp-278h] BYREF
  _DWORD *v44; // [rsp+50h] [rbp-268h]
  void *Block[2]; // [rsp+58h] [rbp-260h] BYREF
  __int64 v46; // [rsp+68h] [rbp-250h]
  WCHAR NewFileName[264]; // [rsp+70h] [rbp-248h] BYREF

  v43[1] = (__int64)this;
  CurrentThread = GetCurrentThread();
  ThreadPriority = GetThreadPriority(CurrentThread);
  Log_Text_F(
    "base\\winsat\\d3d\\graphicsop.cpp",
    193,
    "GraphicsOp::AssessmentThread Launched with priority %d",
    ThreadPriority);
  try
  {
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v43);
    v44 = (_DWORD *)((char *)this + 56);
    *((_DWORD *)this + 14) = 4;
    v4 = (char *)this + 272;
    v42 = 0;
    v5 = 1;
    LOBYTE(v6) = 1;
    if ( (unsigned __int8)mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::has_switch_word(
                            (char *)this + 272,
                            L"wddm10ok",
                            &v42,
                            v6)
      || *((_DWORD *)this + 74) != 1 )
    {
      PrimaryAdapterDriverModel = 0;
    }
    else
    {
      LODWORD(v42) = 0;
      PrimaryAdapterDriverModel = D3DCommon::GetPrimaryAdapterDriverModel((D3DCommon *)&v42, v7);
      if ( PrimaryAdapterDriverModel < 0 )
      {
LABEL_48:
        if ( **(_QWORD **)CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->((__int64)&App::s_AssessmentDumpFileName) )
        {
          memset_0(NewFileName, 0, 0x208u);
          v34 = *((int *)this + 73);
          v35 = &qword_14012B318;
          if ( (_DWORD)v34 == -1 )
            v36 = &qword_14012B318;
          else
            v36 = off_14011D790[v34];
          v37 = *((_DWORD *)this + 74);
          if ( v37 )
          {
            if ( v37 == 1 )
              v35 = L"DX10";
          }
          else
          {
            v35 = L"DX9";
          }
          v38 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->((__int64)&App::s_AssessmentDumpFileName);
          if ( (int)StringCchPrintfW(
                      NewFileName,
                      0x104u,
                      L"%ws.WinSAT.Graphics.%ws%ws.KernelLog.etl",
                      *(_QWORD *)(*(_QWORD *)v38 + 24LL),
                      v36,
                      v35) >= 0 )
            CopyFileW(*(LPCWSTR *)(v43[0] + 24), NewFileName, 0);
        }
        DeleteFileW(*(LPCWSTR *)(v43[0] + 24));
LABEL_59:
        *((_DWORD *)this + 75) = 0;
        *v44 = 6;
        v39 = (char *)*((_QWORD *)this + 9);
        if ( (unsigned __int64)(v39 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
          SetEvent(v39);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v43);
        return 0;
      }
      if ( (_DWORD)v42 != 2 && (_DWORD)v42 != 3 )
      {
        Log_Text_F(
          "base\\winsat\\d3d\\graphicsop.cpp",
          215,
          "Driver is not WDDM 1.1 or WDDM 1.2; aborting DX10 assessment.");
        goto LABEL_48;
      }
    }
    v10 = 0;
    v42 = 0;
    LOBYTE(v8) = 1;
    if ( (unsigned __int8)mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::has_switch_word(
                            (char *)this + 272,
                            L"noetw",
                            &v42,
                            v8) )
    {
      v41 = 0;
      D3DCommon::InitializeETW(v11);
    }
    else
    {
      D3DCommon::InitializeETW(v11);
      if ( (unsigned int)GetTemporaryFile((__int64)L"D3DKernel", (__int64)L"etl", 0, (__int64)v43) )
        goto LABEL_48;
      PrimaryAdapterDriverModel = D3DCommon::StartKernelTracing(*(D3DCommon **)(v43[0] + 24), v12);
      if ( PrimaryAdapterDriverModel < 0 )
      {
        D3DCommon::ERR((D3DCommon *)0x77, v13);
        goto LABEL_48;
      }
      v10 = 1;
      v41 = 1;
    }
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      &v42,
      2048);
    *((_QWORD *)this + 40) = 0;
    if ( *((_DWORD *)this + 73) != -1 )
    {
      v14 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->((__int64)&mlib::stdoutw);
      v15 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)(v14 + 240), (__int64)L"> ");
      v17 = mlib::MUIStr_(
              (mlib *)"base\\winsat\\d3d\\graphicsop.cpp",
              (const char *)0x105,
              (unsigned __int16)word_140141DE8[*((int *)this + 73)],
              v16);
      v18 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v15, (__int64)v17);
      std::endl(v18);
      v4 = (char *)this + 272;
    }
    if ( *(_BYTE *)(CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->((__int64)this + 40)
                  + 495) )
    {
      if ( !dword_1401CBAC0 )
      {
        *((_DWORD *)this + 80) = GetTickCount();
        if ( *((_DWORD *)this + 72) == 1 )
        {
          Log_Text_F(
            "base\\winsat\\d3d\\graphicsop.cpp",
            294,
            "D3D Assessment was called but intentionally not run. Instead, we provide predefined metrics and scores.");
        }
        else if ( *((_DWORD *)this + 74) == 1 )
        {
          if ( *((_BYTE *)this + 32) || (LOBYTE(v25) = 0, *((_BYTE *)this + 33)) )
            LOBYTE(v25) = 1;
          started = SimpleDWM::StartSimpleDWM10(*(_QWORD *)(*(_QWORD *)v4 + 24LL), v24, v25, *((_QWORD *)this + 2));
          PrimaryAdapterDriverModel = started;
          if ( started < 0 )
            Log_Text_F(
              "base\\winsat\\d3d\\graphicsop.cpp",
              304,
              "Error: Failed on StartSimpleDWM10: %x",
              (unsigned int)started);
        }
        else
        {
          v27 = SimpleDWM::StartSimpleDWM(*(unsigned __int16 **)(*(_QWORD *)v4 + 24LL));
          PrimaryAdapterDriverModel = v27;
          if ( v27 < 0 )
            Log_Text_F(
              "base\\winsat\\d3d\\graphicsop.cpp",
              313,
              "ERROR: Failed on StartSimpleDWM: %x",
              (unsigned int)v27);
        }
        *((_DWORD *)this + 81) = GetTickCount();
        if ( PrimaryAdapterDriverModel == -2120548347 )
        {
          v28 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->((__int64)&mlib::stdoutw);
          v29 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)(v28 + 240), (__int64)L"> ");
          v31 = mlib::MUIStr_((mlib *)"base\\winsat\\d3d\\graphicsop.cpp", (const char *)0x145, 10139, v30);
          v32 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v29, (__int64)v31);
          std::endl(v32);
        }
      }
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v42);
      if ( PrimaryAdapterDriverModel >= 0 )
      {
        v33 = v41;
        if ( v41 )
        {
          if ( (int)D3DCommon::StopKernelTracing(v23) < 0 )
            goto LABEL_45;
          *(_OWORD *)Block = 0;
          v46 = 0;
          D3DCommon::ProcessLog(*(_QWORD *)(v43[0] + 24), Block);
          v23 = (D3DCommon *)Block[0];
          if ( (void *)((char *)Block[1] - (char *)Block[0]) == (void *)184 )
          {
            *(_OWORD *)((char *)this + 88) = *(_OWORD *)Block[0];
            *(_OWORD *)((char *)this + 104) = *((_OWORD *)v23 + 1);
            *(_OWORD *)((char *)this + 120) = *((_OWORD *)v23 + 2);
            *(_OWORD *)((char *)this + 136) = *((_OWORD *)v23 + 3);
            *(_OWORD *)((char *)this + 152) = *((_OWORD *)v23 + 4);
            *(_OWORD *)((char *)this + 168) = *((_OWORD *)v23 + 5);
            *(_OWORD *)((char *)this + 184) = *((_OWORD *)v23 + 6);
            *(_OWORD *)((char *)this + 200) = *((_OWORD *)v23 + 7);
            *(_OWORD *)((char *)this + 216) = *((_OWORD *)v23 + 8);
            *(_OWORD *)((char *)this + 232) = *((_OWORD *)v23 + 9);
            *(_OWORD *)((char *)this + 248) = *((_OWORD *)v23 + 10);
            *((_QWORD *)this + 33) = *((_QWORD *)v23 + 22);
          }
          else
          {
            v5 = 0;
          }
          v10 = 0;
          *((_BYTE *)this + 80) = v5;
          if ( v23 )
            operator delete(v23);
        }
        if ( *((_BYTE *)this + 80) && *((_DWORD *)this + 73) != -1 && qword_1401C6668 )
          qword_1401C6668(qword_1401689B8, 1651, (unsigned int)(int)*((double *)this + 11));
LABEL_45:
        if ( v10 )
          D3DCommon::StopKernelTracing(v23);
        if ( !v33 )
          goto LABEL_59;
        goto LABEL_48;
      }
    }
    else
    {
      Log_Text_F("base\\winsat\\d3d\\graphicsop.cpp", 269, "Driver is not WDDM; aborting assessment.");
      v19 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->((__int64)&mlib::stderrw);
      v21 = mlib::MUIStr_((mlib *)"base\\winsat\\d3d\\graphicsop.cpp", (const char *)0x10F, 10054, v20);
      v22 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)(v19 + 240), (__int64)v21);
      std::endl(v22);
      *((_DWORD *)this + 64) = -2120548350;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v42);
    }
    v33 = v41;
    goto LABEL_45;
  }
  catch ( std::bad_alloc )
  {
    return 14;
  }
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v43);
}

```

## disassembly

```asm
0x140079e98  mov     [rsp+arg_8], rbx
0x140079e9d  mov     [rsp+arg_10], rsi
0x140079ea2  push    rdi
0x140079ea3  push    r12
0x140079ea5  push    r13
0x140079ea7  push    r14
0x140079ea9  push    r15
0x140079eab  sub     rsp, 290h
0x140079eb2  mov     rax, cs:__security_cookie
0x140079eb9  xor     rax, rsp
0x140079ebc  mov     [rsp+2B8h+var_38], rax
0x140079ec4  mov     rdi, rcx
0x140079ec7  mov     [rsp+2B8h+var_270], rcx
0x140079ecc  call    cs:__imp_GetCurrentThread
0x140079ed2  mov     rcx, rax; hThread
0x140079ed5  call    cs:__imp_GetThreadPriority
0x140079edb  mov     r9d, eax
0x140079ede  lea     r8, aGraphicsopAsse; "GraphicsOp::AssessmentThread Launched w"...
0x140079ee5  mov     edx, 0C1h
0x140079eea  lea     rcx, aBaseWinsatD3dG; "base\\winsat\\d3d\\graphicsop.cpp"
0x140079ef1  call    Log_Text_F
0x140079ef6  lea     rcx, [rsp+2B8h+var_278]
0x140079efb  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@XZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(void)
0x140079f00  nop
0x140079f01  lea     rax, [rdi+38h]
0x140079f05  mov     [rsp+2B8h+var_268], rax
0x140079f0a  mov     dword ptr [rax], 4
0x140079f10  lea     r12, [rdi+110h]
0x140079f17  xor     ebx, ebx
0x140079f19  mov     [rsp+2B8h+var_280], rbx
0x140079f1e  lea     r15d, [rbx+1]
0x140079f22  mov     r9b, r15b
0x140079f25  lea     r8, [rsp+2B8h+var_280]
0x140079f2a  lea     rdx, aWddm10ok; "wddm10ok"
0x140079f31  mov     rcx, r12
0x140079f34  call    ?has_switch_word@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA_NPEBGAEA_K_N@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::has_switch_word(ushort const *,unsigned __int64 &,bool)
0x140079f39  test    al, al
0x140079f3b  jnz     short loc_140079F8C
0x140079f3d  cmp     [rdi+128h], r15d
0x140079f44  jnz     short loc_140079F8C
0x140079f46  mov     dword ptr [rsp+2B8h+var_280], ebx
0x140079f4a  lea     rcx, [rsp+2B8h+var_280]; this
0x140079f4f  call    ?GetPrimaryAdapterDriverModel@D3DCommon@@YAJAEAW4tag_EVideoDriverModel@1@@Z; D3DCommon::GetPrimaryAdapterDriverModel(D3DCommon::tag_EVideoDriverModel &)
0x140079f54  mov     esi, eax
0x140079f56  test    eax, eax
0x140079f58  js      short loc_140079F80
0x140079f5a  cmp     dword ptr [rsp+2B8h+var_280], 2
0x140079f5f  jz      short loc_140079F8E
0x140079f61  cmp     dword ptr [rsp+2B8h+var_280], 3
0x140079f66  jz      short loc_140079F8E
0x140079f68  lea     r8, aDriverIsNotWdd; "Driver is not WDDM 1.1 or WDDM 1.2; abo"...
0x140079f6f  mov     edx, 0D7h
0x140079f74  lea     rcx, aBaseWinsatD3dG; "base\\winsat\\d3d\\graphicsop.cpp"
0x140079f7b  call    Log_Text_F
0x140079f80  lea     r13, cs:140000000h
0x140079f87  jmp     loc_14007A39B
0x140079f8c  mov     esi, ebx
0x140079f8e  mov     r14b, bl
0x140079f91  mov     [rsp+2B8h+var_288], bl
0x140079f95  mov     [rsp+2B8h+var_280], rbx
0x140079f9a  mov     r9b, r15b
0x140079f9d  lea     r8, [rsp+2B8h+var_280]
0x140079fa2  lea     rdx, aNoetw; "noetw"
0x140079fa9  mov     rcx, r12
0x140079fac  call    ?has_switch_word@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA_NPEBGAEA_K_N@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::has_switch_word(ushort const *,unsigned __int64 &,bool)
0x140079fb1  test    al, al
0x140079fb3  jnz     short loc_14007A008
0x140079fb5  call    ?InitializeETW@D3DCommon@@YAXXZ; D3DCommon::InitializeETW(void)
0x140079fba  lea     r9, [rsp+2B8h+var_278]
0x140079fbf  xor     r8d, r8d
0x140079fc2  lea     rdx, aEtl_0; "etl"
0x140079fc9  lea     rcx, aD3dkernel; "D3DKernel"
0x140079fd0  call    ?GetTemporaryFile@@YAKPEBG00AEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@Z; GetTemporaryFile(ushort const *,ushort const *,ushort const *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> &)
0x140079fd5  test    eax, eax
0x140079fd7  jnz     short loc_140079F80
0x140079fd9  mov     rcx, [rsp+2B8h+var_278]
0x140079fde  mov     rcx, [rcx+18h]; this
0x140079fe2  call    ?StartKernelTracing@D3DCommon@@YAJPEBG@Z; D3DCommon::StartKernelTracing(ushort const *)
0x140079fe7  mov     esi, eax
0x140079fe9  test    eax, eax
0x140079feb  jns     short loc_140079FF9
0x140079fed  mov     ecx, 77h ; 'w'; this
0x140079ff2  call    ?ERR@D3DCommon@@YAXGZZ; D3DCommon::ERR(ushort,...)
0x140079ff7  jmp     short loc_140079F80
0x140079ff9  mov     r14b, r15b
0x140079ffc  mov     [rsp+2B8h+var_288], r15b
0x14007a001  mov     [rsp+2B8h+var_287], r15b
0x14007a006  jmp     short loc_14007A012
0x14007a008  mov     [rsp+2B8h+var_287], bl
0x14007a00c  call    ?InitializeETW@D3DCommon@@YAXXZ; D3DCommon::InitializeETW(void)
0x14007a011  nop
0x14007a012  mov     edx, 800h
0x14007a017  lea     rcx, [rsp+2B8h+var_280]
0x14007a01c  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@_K@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(unsigned __int64)
0x14007a021  nop
0x14007a022  mov     [rdi+140h], rbx
0x14007a029  cmp     dword ptr [rdi+124h], 0FFFFFFFFh
0x14007a030  jz      short loc_14007A098
0x14007a032  lea     rcx, ?stdoutw@mlib@@3V?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@A; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>> mlib::stdoutw
0x14007a039  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x14007a03e  lea     rcx, [rax+0F0h]
0x14007a045  lea     rdx, asc_14012C580; "> "
0x14007a04c  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14007a051  mov     r12, rax
0x14007a054  movsxd  r8, dword ptr [rdi+124h]
0x14007a05b  lea     r13, cs:140000000h
0x14007a062  movzx   r8d, ds:rva word_140141DE8[r13+r8*2]; int
0x14007a06b  mov     edx, 105h; char *
0x14007a070  lea     rcx, aBaseWinsatD3dG; "base\\winsat\\d3d\\graphicsop.cpp"
0x14007a077  call    ?MUIStr_@mlib@@YAPEBGPEBDHG@Z; mlib::MUIStr_(char const *,int,ushort)
0x14007a07c  mov     rdx, rax
0x14007a07f  mov     rcx, r12
0x14007a082  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14007a087  mov     rcx, rax
0x14007a08a  call    ?endl@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@1@AEAV21@@Z; std::endl(std::basic_ostream<ushort> &)
0x14007a08f  lea     r12, [rdi+110h]
0x14007a096  jmp     short loc_14007A09F
0x14007a098  lea     r13, cs:140000000h
0x14007a09f  lea     rcx, [rdi+28h]
0x14007a0a3  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x14007a0a8  cmp     [rax+1EFh], bl
0x14007a0ae  jnz     short loc_14007A11F
0x14007a0b0  lea     r8, aDriverIsNotWdd_0; "Driver is not WDDM; aborting assessment"...
0x14007a0b7  mov     edx, 10Dh
0x14007a0bc  lea     rcx, aBaseWinsatD3dG; "base\\winsat\\d3d\\graphicsop.cpp"
0x14007a0c3  call    Log_Text_F
0x14007a0c8  lea     rcx, ?stderrw@mlib@@3V?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@A; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>> mlib::stderrw
0x14007a0cf  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x14007a0d4  mov     rsi, rax
0x14007a0d7  mov     edx, 10Fh; char *
0x14007a0dc  mov     r8d, 2746h; int
0x14007a0e2  lea     rcx, aBaseWinsatD3dG; "base\\winsat\\d3d\\graphicsop.cpp"
0x14007a0e9  call    ?MUIStr_@mlib@@YAPEBGPEBDHG@Z; mlib::MUIStr_(char const *,int,ushort)
0x14007a0ee  lea     rcx, [rsi+0F0h]
0x14007a0f5  mov     rdx, rax
0x14007a0f8  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14007a0fd  mov     rcx, rax
0x14007a100  call    ?endl@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@1@AEAV21@@Z; std::endl(std::basic_ostream<ushort> &)
0x14007a105  mov     dword ptr [rdi+100h], 819B0002h
0x14007a10f  lea     rcx, [rsp+2B8h+var_280]
0x14007a114  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x14007a119  nop
0x14007a11a  jmp     loc_14007A383
0x14007a11f  mov     eax, cs:dword_1401CBAC0
0x14007a125  test    eax, eax
0x14007a127  jnz     loc_14007A239
0x14007a12d  call    cs:__imp_GetTickCount
0x14007a133  mov     [rdi+140h], eax
0x14007a139  cmp     dword ptr [rdi+120h], 1
0x14007a140  jz      short loc_14007A1C0
0x14007a142  mov     r9, [rdi+10h]
0x14007a146  cmp     [rdi+128h], r15d
0x14007a14d  jnz     short loc_14007A18F
0x14007a14f  cmp     [rdi+20h], bl
0x14007a152  jnz     short loc_14007A15C
0x14007a154  cmp     [rdi+21h], bl
0x14007a157  mov     r8b, bl
0x14007a15a  jz      short loc_14007A15F
0x14007a15c  mov     r8b, r15b
0x14007a15f  mov     rcx, [r12]
0x14007a163  mov     rcx, [rcx+18h]
0x14007a167  call    ?StartSimpleDWM10@SimpleDWM@@YAJPEBGK_NPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@Z; SimpleDWM::StartSimpleDWM10(ushort const *,ulong,bool,mlib::handle_ostreamT<ushort,std::char_traits<ushort>> *)
0x14007a16c  mov     esi, eax
0x14007a16e  test    eax, eax
0x14007a170  jns     short loc_14007A1D8
0x14007a172  lea     r8, aErrorFailedOnS_0; "Error: Failed on StartSimpleDWM10: %x"
0x14007a179  mov     edx, 130h
0x14007a17e  mov     r9d, eax
0x14007a181  lea     rcx, aBaseWinsatD3dG; "base\\winsat\\d3d\\graphicsop.cpp"
0x14007a188  call    Log_Text_F
0x14007a18d  jmp     short loc_14007A1D8
0x14007a18f  cmp     [rdi+20h], bl
0x14007a192  jnz     short loc_14007A19C
0x14007a194  cmp     [rdi+21h], bl
0x14007a197  mov     r8b, bl
0x14007a19a  jz      short loc_14007A19F
0x14007a19c  mov     r8b, r15b
0x14007a19f  mov     rcx, [r12]
0x14007a1a3  mov     rcx, [rcx+18h]; unsigned __int16 *
0x14007a1a7  call    ?StartSimpleDWM@SimpleDWM@@YAJPEBGK_NPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@Z; SimpleDWM::StartSimpleDWM(ushort const *,ulong,bool,mlib::handle_ostreamT<ushort,std::char_traits<ushort>> *)
0x14007a1ac  mov     esi, eax
0x14007a1ae  test    eax, eax
0x14007a1b0  jns     short loc_14007A1D8
0x14007a1b2  lea     r8, aErrorFailedOnS; "ERROR: Failed on StartSimpleDWM: %x"
0x14007a1b9  mov     edx, 139h
0x14007a1be  jmp     short loc_14007A17E
0x14007a1c0  lea     r8, aD3dAssessmentW; "D3D Assessment was called but intention"...
0x14007a1c7  mov     edx, 126h
0x14007a1cc  lea     rcx, aBaseWinsatD3dG; "base\\winsat\\d3d\\graphicsop.cpp"
0x14007a1d3  call    Log_Text_F
0x14007a1d8  call    cs:__imp_GetTickCount
0x14007a1de  mov     [rdi+144h], eax
0x14007a1e4  cmp     esi, 819B0005h
0x14007a1ea  jnz     short loc_14007A239
0x14007a1ec  lea     rcx, ?stdoutw@mlib@@3V?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@A; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>> mlib::stdoutw
0x14007a1f3  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x14007a1f8  lea     rcx, [rax+0F0h]
0x14007a1ff  lea     rdx, asc_14012C580; "> "
0x14007a206  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14007a20b  mov     r12, rax
0x14007a20e  mov     edx, 145h; char *
0x14007a213  mov     r8d, 279Bh; int
0x14007a219  lea     rcx, aBaseWinsatD3dG; "base\\winsat\\d3d\\graphicsop.cpp"
0x14007a220  call    ?MUIStr_@mlib@@YAPEBGPEBDHG@Z; mlib::MUIStr_(char const *,int,ushort)
0x14007a225  mov     rdx, rax
0x14007a228  mov     rcx, r12
0x14007a22b  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14007a230  mov     rcx, rax
0x14007a233  call    ?endl@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@1@AEAV21@@Z; std::endl(std::basic_ostream<ushort> &)
0x14007a238  nop
0x14007a239  lea     rcx, [rsp+2B8h+var_280]
0x14007a23e  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x14007a243  nop
0x14007a244  test    esi, esi
0x14007a246  js      loc_14007A383
0x14007a24c  mov     sil, [rsp+2B8h+var_287]
0x14007a251  test    sil, sil
0x14007a254  jz      loc_14007A33D
0x14007a25a  call    ?StopKernelTracing@D3DCommon@@YAJXZ; D3DCommon::StopKernelTracing(void)
0x14007a25f  test    eax, eax
0x14007a261  js      loc_14007A388
0x14007a267  xorps   xmm0, xmm0
0x14007a26a  movdqu  xmmword ptr [rsp+2B8h+Block], xmm0
0x14007a270  mov     [rsp+2B8h+var_250], rbx
0x14007a275  lea     rdx, [rsp+2B8h+Block]
0x14007a27a  mov     rcx, [rsp+2B8h+var_278]
0x14007a27f  mov     rcx, [rcx+18h]
0x14007a283  call    ?ProcessLog@D3DCommon@@YAJPEBGAEAV?$vector@U_AssessmentResults@D3DCommon@@V?$allocator@U_AssessmentResults@D3DCommon@@@std@@@std@@@Z; D3DCommon::ProcessLog(ushort const *,std::vector<D3DCommon::_AssessmentResults> &)
0x14007a288  mov     rax, [rsp+2B8h+Block+8]
0x14007a28d  mov     rcx, [rsp+2B8h+Block]; Block
0x14007a292  sub     rax, rcx
0x14007a295  cmp     rax, 0B8h
0x14007a29b  jnz     loc_14007A329
0x14007a2a1  movups  xmm0, xmmword ptr [rcx]
0x14007a2a4  movups  xmmword ptr [rdi+58h], xmm0
0x14007a2a8  movups  xmm1, xmmword ptr [rcx+10h]
0x14007a2ac  movups  xmmword ptr [rdi+68h], xmm1
0x14007a2b0  movups  xmm0, xmmword ptr [rcx+20h]
0x14007a2b4  movups  xmmword ptr [rdi+78h], xmm0
0x14007a2b8  movups  xmm1, xmmword ptr [rcx+30h]
0x14007a2bc  movups  xmmword ptr [rdi+88h], xmm1
0x14007a2c3  movups  xmm0, xmmword ptr [rcx+40h]
0x14007a2c7  movups  xmmword ptr [rdi+98h], xmm0
0x14007a2ce  movups  xmm1, xmmword ptr [rcx+50h]
0x14007a2d2  movups  xmmword ptr [rdi+0A8h], xmm1
0x14007a2d9  movups  xmm0, xmmword ptr [rcx+60h]
0x14007a2dd  movups  xmmword ptr [rdi+0B8h], xmm0
0x14007a2e4  movups  xmm1, xmmword ptr [rcx+70h]
0x14007a2e8  movups  xmmword ptr [rdi+0C8h], xmm1
0x14007a2ef  movups  xmm0, xmmword ptr [rcx+80h]
0x14007a2f6  movups  xmmword ptr [rdi+0D8h], xmm0
0x14007a2fd  movups  xmm1, xmmword ptr [rcx+90h]
0x14007a304  movups  xmmword ptr [rdi+0E8h], xmm1
0x14007a30b  movups  xmm0, xmmword ptr [rcx+0A0h]
0x14007a312  movups  xmmword ptr [rdi+0F8h], xmm0
0x14007a319  mov     rax, [rcx+0B0h]
0x14007a320  mov     [rdi+108h], rax
0x14007a327  jmp     short loc_14007A32C
0x14007a329  mov     r15b, bl
0x14007a32c  mov     r14b, bl
0x14007a32f  mov     [rdi+50h], r15b
0x14007a333  test    rcx, rcx
0x14007a336  jz      short loc_14007A33D
0x14007a338  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14007a33d  cmp     [rdi+50h], bl
0x14007a340  jz      short loc_14007A388
0x14007a342  cmp     dword ptr [rdi+124h], 0FFFFFFFFh
0x14007a349  jz      short loc_14007A388
0x14007a34b  mov     rax, cs:qword_1401C6668
0x14007a352  test    rax, rax
0x14007a355  jz      short loc_14007A388
0x14007a357  cvttsd2si r8, qword ptr [rdi+58h]
0x14007a35d  mov     edx, 673h
0x14007a362  lea     rcx, qword_1401689B8
0x14007a369  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007a36e  jmp     short loc_14007A388
0x14007a370  xor     ebx, ebx
0x14007a372  lea     r13, cs:140000000h
0x14007a379  mov     r14b, [rsp+2B8h+var_288]
0x14007a37e  mov     rdi, [rsp+2B8h+var_270]
0x14007a383  mov     sil, [rsp+2B8h+var_287]
0x14007a388  test    r14b, r14b
0x14007a38b  jz      short loc_14007A392
0x14007a38d  call    ?StopKernelTracing@D3DCommon@@YAJXZ; D3DCommon::StopKernelTracing(void)
0x14007a392  test    sil, sil
0x14007a395  jz      loc_14007A461
0x14007a39b  lea     rcx, ?s_AssessmentDumpFileName@App@@2V?$CSmartPtr@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@@A; CSmartPtr<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>> App::s_AssessmentDumpFileName
0x14007a3a2  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x14007a3a7  mov     rax, [rax]
0x14007a3aa  cmp     [rax], rbx
0x14007a3ad  jz      loc_14007A452
0x14007a3b3  xor     edx, edx; Val
0x14007a3b5  mov     r8d, 208h; Size
0x14007a3bb  lea     rcx, [rsp+2B8h+NewFileName]; void *
0x14007a3c0  call    memset_0
0x14007a3c5  movsxd  rax, dword ptr [rdi+124h]
0x14007a3cc  lea     rsi, qword_14012B318
0x14007a3d3  cmp     eax, 0FFFFFFFFh
0x14007a3d6  jz      short loc_14007A3E2
0x14007a3d8  mov     r14, ds:rva off_14011D790[r13+rax*8]; "DWM" ...
  ... truncated ...
```
