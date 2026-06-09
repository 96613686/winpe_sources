# ProcessWinSATError(int)

- ea: `0x14003b020`
- end: `0x14003b620`
- name: `?ProcessWinSATError@@YAXH@Z`
- size: `1536`
- prototype: `void __fastcall(char)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config`

## callers

- `0x14001a54c`

## callees

- `0x140005d78`
- `0x140005f10`
- `0x1400085b4`
- `0x140008ac4`
- `0x140016480`
- `0x14001669c`
- `0x140016d04`
- `0x140018968`
- `0x140021b58`
- `0x14002c48c`
- `0x14003af74`
- `0x14003b020`
- `0x14003b8bc`
- `0x14003ec14`
- `0x14003fa8c`
- `0x14005354c`
- `0x140053590`
- `0x1400535e4`
- `0x140053618`
- `0x140053bf0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14003b50a`
- `KERNEL32!GetLastError` at `0x14003b54c`
- `KERNEL32!GetLastError` at `0x14003b58f`
- `KERNEL32!GetLastError` at `0x14003b50a`
- `KERNEL32!GetLastError` at `0x14003b54c`
- `KERNEL32!GetLastError` at `0x14003b58f`

## string_xrefs

- `0x14003b3fd`: `Writing exit code, cant msg and why msg to registry `
- `0x14003b517`: `Can't write last exit code %u to the registry`
- `0x14003b557`: `Can't write error message '%s' to the registry`
- `0x14003b59a`: `Can't write error message '%s' to the registry`
- `0x14003b5de`: `Skipping writing the exit code, cant msg and why msg to registry`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
void __fastcall ProcessWinSATError(int a1)
{
  __int64 v2; // rdx
  bool v3; // al
  __int64 v4; // rax
  __int64 v5; // rbx
  __int64 v6; // rbx
  _QWORD v7[2]; // [rsp+30h] [rbp-128h] BYREF
  _QWORD v8[10]; // [rsp+40h] [rbp-118h] BYREF
  _QWORD v9[12]; // [rsp+90h] [rbp-C8h] BYREF
  _QWORD v10[13]; // [rsp+F0h] [rbp-68h] BYREF
  __int64 v11; // [rsp+168h] [rbp+10h] BYREF
  __int64 v12; // [rsp+170h] [rbp+18h] BYREF
  __int64 v13; // [rsp+178h] [rbp+20h] BYREF

  try
  {
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(&v11);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(&v12);
    if ( a1 > 7 )
    {
      switch ( a1 )
      {
        case 8:
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::LoadMessageFromModule(
            &v11,
            18);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::LoadMessageFromModule(
            &v12,
            19);
          goto LABEL_46;
        case 9:
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::LoadMessageFromModule(
            &v11,
            20);
          v2 = 21;
          goto LABEL_17;
        case 10:
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::LoadMessageFromModule(
            &v11,
            22);
          v2 = 23;
          goto LABEL_17;
        case 11:
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::LoadMessageFromModule(
            &v11,
            24);
          v2 = 25;
          goto LABEL_17;
        case 12:
          if ( qword_1401C3370 )
          {
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::attach_buf(
              &v11,
              *(_QWORD *)qword_1401C3370);
            if ( qword_1401C3370 )
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::`scalar deleting destructor'(qword_1401C3370);
            qword_1401C3370 = 0;
          }
          else
          {
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::LoadMessageFromModule(
              &v11,
              30);
          }
          v2 = 31;
          goto LABEL_17;
        case 13:
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::LoadMessageFromModule(
            &v11,
            28);
          v2 = 29;
          goto LABEL_17;
        case 14:
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::LoadMessageFromModule(
            &v11,
            32);
          v2 = 33;
          goto LABEL_17;
      }
    }
    else
    {
      if ( a1 == 7 )
      {
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::LoadMessageFromModule(
          &v11,
          16);
        v2 = 17;
        goto LABEL_17;
      }
      if ( !a1 )
      {
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::LoadMessageFromModule(
          &v11,
          2);
        v2 = 3;
        goto LABEL_17;
      }
      if ( a1 != 1 )
      {
        switch ( a1 )
        {
          case 2:
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::LoadMessageFromModule(
              &v11,
              6);
            v2 = 7;
            goto LABEL_17;
          case 3:
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::LoadMessageFromModule(
              &v11,
              8);
            v2 = 9;
            goto LABEL_17;
          case 4:
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::LoadMessageFromModule(
              &v11,
              10);
            v2 = 11;
            goto LABEL_17;
          case 5:
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::LoadMessageFromModule(
              &v11,
              12);
            v2 = 13;
            goto LABEL_17;
          case 6:
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::LoadMessageFromModule(
              &v11,
              14);
            v2 = 15;
LABEL_17:
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::LoadMessageFromModule(
              &v12,
              v2);
            goto LABEL_46;
        }
      }
    }
    Log_Text_F((__int64)"base\\winsat\\exe\\processwinsaterror.cpp", 298, "Unspecified error %u occured.", a1);
    if ( !qword_1401C3370 || !qword_1401C3378 )
    {
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::LoadMessageFromModule(
        &v11,
        4);
      v2 = 5;
      goto LABEL_17;
    }
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::attach_buf(
      &v11,
      *(_QWORD *)qword_1401C3370);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::attach_buf(
      &v12,
      *(_QWORD *)qword_1401C3378);
    if ( qword_1401C3370 )
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::`scalar deleting destructor'(qword_1401C3370);
    qword_1401C3370 = 0;
    if ( qword_1401C3378 )
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::`scalar deleting destructor'(qword_1401C3378);
    qword_1401C3378 = 0;
LABEL_46:
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::collapse_ws(&v11);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::collapse_ws(&v12);
    if ( a1 )
    {
      v3 = App::s_isAxeMode;
      if ( !App::s_isAxeMode )
        goto LABEL_50;
      v13 = 0;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::attach_buf(
        &v13,
        v12);
      v7[0] = 0;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::attach_buf(
        v7,
        v11);
      WriteFailureToAxeResultsXML((__int64)v7, (__int64)&v13, a1);
    }
    v3 = App::s_isAxeMode;
LABEL_50:
    if ( v3
      || (v4 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->((__int64)&App::s_xmlTestFile),
          !(unsigned __int8)mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::is_blank(v4))
      || App::s_WsSwapTest
      || !App::s_RegistryCreated )
    {
      Log_Text_F(
        (__int64)"base\\winsat\\exe\\processwinsaterror.cpp",
        340,
        "Skipping writing the exit code, cant msg and why msg to registry");
    }
    else
    {
      Log_Text_F(
        (__int64)"base\\winsat\\exe\\processwinsaterror.cpp",
        319,
        "Writing exit code, cant msg and why msg to registry ");
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        &v13,
        L"LastExitCode");
      mlib::DWORDReg::DWORDReg(v8);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v13);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        v7,
        L"LastExitCodeCantMsg");
      mlib::RstringReg::RstringReg(v10);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v7);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        &v13,
        L"LastExitCodeWhyMsg");
      mlib::RstringReg::RstringReg(v9);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v13);
      mlib::DWORDReg::operator=(v8, (unsigned int)a1);
      mlib::RstringReg::operator=(v10, &v11);
      mlib::RstringReg::operator=(v9, &v12);
      if ( (unsigned int)mlib::MRegistryRWBase::write((mlib::MRegistryRWBase *)v8) )
      {
        GetLastError();
        Record_Win32Error_w("base\\winsat\\exe\\processwinsaterror.cpp", a1);
      }
      if ( (unsigned int)mlib::MRegistryRWBase::write((mlib::MRegistryRWBase *)v10) )
      {
        v5 = *(_QWORD *)(v11 + 24);
        GetLastError();
        Record_Win32Error_w("base\\winsat\\exe\\processwinsaterror.cpp", v5);
      }
      if ( (unsigned int)mlib::MRegistryRWBase::write((mlib::MRegistryRWBase *)v9) )
      {
        v6 = *(_QWORD *)(v12 + 24);
        GetLastError();
        Record_Win32Error_w("base\\winsat\\exe\\processwinsaterror.cpp", v6);
      }
      mlib::RstringReg::~RstringReg((mlib::RstringReg *)v9);
      mlib::RstringReg::~RstringReg((mlib::RstringReg *)v10);
      mlib::DWORDReg::~DWORDReg((mlib::DWORDReg *)v8);
    }
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v12);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v11);
  }
  catch ( std::bad_alloc )
  {
    Log_Text_F(
      (__int64)"base\\winsat\\exe\\processwinsaterror.cpp",
      344,
      "ERROR: Out of memory while attempting to save exit code data to the registy");
    return;
  }
  catch ( ... )
  {
    Log_Text_F(
      (__int64)"base\\winsat\\exe\\processwinsaterror.cpp",
      346,
      "ERROR: Unhandled while attempting to save exit code data to the registy");
  }
}

```

## disassembly

```asm
0x14003b020  mov     rax, rsp
0x14003b023  push    rbx
0x14003b024  sub     rsp, 150h
0x14003b02b  mov     ebx, ecx
0x14003b02d  lea     rcx, [rax+10h]
0x14003b031  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@XZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(void)
0x14003b036  nop
0x14003b037  lea     rcx, [rsp+158h+arg_10]
0x14003b03f  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@XZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(void)
0x14003b044  nop
0x14003b045  cmp     ebx, 7
0x14003b048  jg      loc_14003B141
0x14003b04e  jz      loc_14003B128
0x14003b054  mov     ecx, ebx
0x14003b056  test    ebx, ebx
0x14003b058  jz      loc_14003B0FF
0x14003b05e  sub     ecx, 1
0x14003b061  jz      loc_14003B182
0x14003b067  sub     ecx, 1
0x14003b06a  jz      short loc_14003B0E6
0x14003b06c  sub     ecx, 1
0x14003b06f  jz      short loc_14003B0CD
0x14003b071  sub     ecx, 1
0x14003b074  jz      short loc_14003B0B4
0x14003b076  sub     ecx, 1
0x14003b079  jz      short loc_14003B09B
0x14003b07b  cmp     ecx, 1
0x14003b07e  jnz     loc_14003B182
0x14003b084  lea     edx, [rcx+0Dh]
0x14003b087  lea     rcx, [rsp+158h+arg_8]
0x14003b08f  call    ?LoadMessageFromModule@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAKKPEAUHINSTANCE__@@K@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::LoadMessageFromModule(ulong,HINSTANCE__ *,ulong)
0x14003b094  mov     edx, 0Fh
0x14003b099  jmp     short loc_14003B116
0x14003b09b  mov     edx, 0Ch
0x14003b0a0  lea     rcx, [rsp+158h+arg_8]
0x14003b0a8  call    ?LoadMessageFromModule@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAKKPEAUHINSTANCE__@@K@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::LoadMessageFromModule(ulong,HINSTANCE__ *,ulong)
0x14003b0ad  mov     edx, 0Dh
0x14003b0b2  jmp     short loc_14003B116
0x14003b0b4  mov     edx, 0Ah
0x14003b0b9  lea     rcx, [rsp+158h+arg_8]
0x14003b0c1  call    ?LoadMessageFromModule@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAKKPEAUHINSTANCE__@@K@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::LoadMessageFromModule(ulong,HINSTANCE__ *,ulong)
0x14003b0c6  mov     edx, 0Bh
0x14003b0cb  jmp     short loc_14003B116
0x14003b0cd  mov     edx, 8
0x14003b0d2  lea     rcx, [rsp+158h+arg_8]
0x14003b0da  call    ?LoadMessageFromModule@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAKKPEAUHINSTANCE__@@K@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::LoadMessageFromModule(ulong,HINSTANCE__ *,ulong)
0x14003b0df  mov     edx, 9
0x14003b0e4  jmp     short loc_14003B116
0x14003b0e6  mov     edx, 6
0x14003b0eb  lea     rcx, [rsp+158h+arg_8]
0x14003b0f3  call    ?LoadMessageFromModule@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAKKPEAUHINSTANCE__@@K@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::LoadMessageFromModule(ulong,HINSTANCE__ *,ulong)
0x14003b0f8  mov     edx, 7
0x14003b0fd  jmp     short loc_14003B116
0x14003b0ff  mov     edx, 2
0x14003b104  lea     rcx, [rsp+158h+arg_8]
0x14003b10c  call    ?LoadMessageFromModule@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAKKPEAUHINSTANCE__@@K@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::LoadMessageFromModule(ulong,HINSTANCE__ *,ulong)
0x14003b111  mov     edx, 3
0x14003b116  lea     rcx, [rsp+158h+arg_10]
0x14003b11e  call    ?LoadMessageFromModule@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAKKPEAUHINSTANCE__@@K@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::LoadMessageFromModule(ulong,HINSTANCE__ *,ulong)
0x14003b123  jmp     loc_14003B340
0x14003b128  mov     edx, 10h
0x14003b12d  lea     rcx, [rsp+158h+arg_8]
0x14003b135  call    ?LoadMessageFromModule@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAKKPEAUHINSTANCE__@@K@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::LoadMessageFromModule(ulong,HINSTANCE__ *,ulong)
0x14003b13a  mov     edx, 11h
0x14003b13f  jmp     short loc_14003B116
0x14003b141  mov     ecx, ebx
0x14003b143  sub     ecx, 8
0x14003b146  jz      loc_14003B31C
0x14003b14c  sub     ecx, 1
0x14003b14f  jz      loc_14003B300
0x14003b155  sub     ecx, 1
0x14003b158  jz      loc_14003B2E4
0x14003b15e  sub     ecx, 1
0x14003b161  jz      loc_14003B2C8
0x14003b167  sub     ecx, 1
0x14003b16a  jz      loc_14003B275
0x14003b170  sub     ecx, 1
0x14003b173  jz      loc_14003B259
0x14003b179  cmp     ecx, 1
0x14003b17c  jz      loc_14003B23D
0x14003b182  mov     r9d, ebx
0x14003b185  lea     r8, aUnspecifiedErr; "Unspecified error %u occured."
0x14003b18c  mov     edx, 12Ah
0x14003b191  lea     rcx, aBaseWinsatExeP_0; "base\\winsat\\exe\\processwinsaterror.c"...
0x14003b198  call    Log_Text_F
0x14003b19d  mov     rdx, cs:qword_1401C3370
0x14003b1a4  test    rdx, rdx
0x14003b1a7  jz      short loc_14003B221
0x14003b1a9  cmp     cs:qword_1401C3378, 0
0x14003b1b1  jz      short loc_14003B221
0x14003b1b3  mov     rdx, [rdx]
0x14003b1b6  lea     rcx, [rsp+158h+arg_8]
0x14003b1be  call    ?attach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXPEAV?$mstring_buf@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::attach_buf(mlib::mstring_buf<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x14003b1c3  mov     rdx, cs:qword_1401C3378
0x14003b1ca  mov     rdx, [rdx]
0x14003b1cd  lea     rcx, [rsp+158h+arg_10]
0x14003b1d5  call    ?attach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXPEAV?$mstring_buf@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::attach_buf(mlib::mstring_buf<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x14003b1da  mov     rcx, cs:qword_1401C3370; Block
0x14003b1e1  test    rcx, rcx
0x14003b1e4  jz      short loc_14003B1F0
0x14003b1e6  mov     edx, 1
0x14003b1eb  call    ??_G?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAPEAXI@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::`scalar deleting destructor'(uint)
0x14003b1f0  mov     cs:qword_1401C3370, 0
0x14003b1fb  mov     rcx, cs:qword_1401C3378; Block
0x14003b202  test    rcx, rcx
0x14003b205  jz      short loc_14003B211
0x14003b207  mov     edx, 1
0x14003b20c  call    ??_G?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAPEAXI@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::`scalar deleting destructor'(uint)
0x14003b211  mov     cs:qword_1401C3378, 0
0x14003b21c  jmp     loc_14003B340
0x14003b221  mov     edx, 4
0x14003b226  lea     rcx, [rsp+158h+arg_8]
0x14003b22e  call    ?LoadMessageFromModule@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAKKPEAUHINSTANCE__@@K@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::LoadMessageFromModule(ulong,HINSTANCE__ *,ulong)
0x14003b233  mov     edx, 5
0x14003b238  jmp     loc_14003B116
0x14003b23d  mov     edx, 20h ; ' '
0x14003b242  lea     rcx, [rsp+158h+arg_8]
0x14003b24a  call    ?LoadMessageFromModule@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAKKPEAUHINSTANCE__@@K@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::LoadMessageFromModule(ulong,HINSTANCE__ *,ulong)
0x14003b24f  mov     edx, 21h ; '!'
0x14003b254  jmp     loc_14003B116
0x14003b259  mov     edx, 1Ch
0x14003b25e  lea     rcx, [rsp+158h+arg_8]
0x14003b266  call    ?LoadMessageFromModule@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAKKPEAUHINSTANCE__@@K@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::LoadMessageFromModule(ulong,HINSTANCE__ *,ulong)
0x14003b26b  mov     edx, 1Dh
0x14003b270  jmp     loc_14003B116
0x14003b275  mov     rdx, cs:qword_1401C3370
0x14003b27c  lea     rcx, [rsp+158h+arg_8]
0x14003b284  test    rdx, rdx
0x14003b287  jz      short loc_14003B2B4
0x14003b289  mov     rdx, [rdx]
0x14003b28c  call    ?attach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXPEAV?$mstring_buf@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::attach_buf(mlib::mstring_buf<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x14003b291  mov     rcx, cs:qword_1401C3370; Block
0x14003b298  test    rcx, rcx
0x14003b29b  jz      short loc_14003B2A7
0x14003b29d  mov     edx, 1
0x14003b2a2  call    ??_G?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAPEAXI@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::`scalar deleting destructor'(uint)
0x14003b2a7  mov     cs:qword_1401C3370, 0
0x14003b2b2  jmp     short loc_14003B2BE
0x14003b2b4  mov     edx, 1Eh
0x14003b2b9  call    ?LoadMessageFromModule@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAKKPEAUHINSTANCE__@@K@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::LoadMessageFromModule(ulong,HINSTANCE__ *,ulong)
0x14003b2be  mov     edx, 1Fh
0x14003b2c3  jmp     loc_14003B116
0x14003b2c8  mov     edx, 18h
0x14003b2cd  lea     rcx, [rsp+158h+arg_8]
0x14003b2d5  call    ?LoadMessageFromModule@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAKKPEAUHINSTANCE__@@K@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::LoadMessageFromModule(ulong,HINSTANCE__ *,ulong)
0x14003b2da  mov     edx, 19h
0x14003b2df  jmp     loc_14003B116
0x14003b2e4  mov     edx, 16h
0x14003b2e9  lea     rcx, [rsp+158h+arg_8]
0x14003b2f1  call    ?LoadMessageFromModule@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAKKPEAUHINSTANCE__@@K@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::LoadMessageFromModule(ulong,HINSTANCE__ *,ulong)
0x14003b2f6  mov     edx, 17h
0x14003b2fb  jmp     loc_14003B116
0x14003b300  mov     edx, 14h
0x14003b305  lea     rcx, [rsp+158h+arg_8]
0x14003b30d  call    ?LoadMessageFromModule@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAKKPEAUHINSTANCE__@@K@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::LoadMessageFromModule(ulong,HINSTANCE__ *,ulong)
0x14003b312  mov     edx, 15h
0x14003b317  jmp     loc_14003B116
0x14003b31c  mov     edx, 12h
0x14003b321  lea     rcx, [rsp+158h+arg_8]
0x14003b329  call    ?LoadMessageFromModule@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAKKPEAUHINSTANCE__@@K@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::LoadMessageFromModule(ulong,HINSTANCE__ *,ulong)
0x14003b32e  mov     edx, 13h
0x14003b333  lea     rcx, [rsp+158h+arg_10]
0x14003b33b  call    ?LoadMessageFromModule@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAKKPEAUHINSTANCE__@@K@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::LoadMessageFromModule(ulong,HINSTANCE__ *,ulong)
0x14003b340  lea     rcx, [rsp+158h+arg_8]
0x14003b348  call    ?collapse_ws@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::collapse_ws(void)
0x14003b34d  lea     rcx, [rsp+158h+arg_10]
0x14003b355  call    ?collapse_ws@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::collapse_ws(void)
0x14003b35a  test    ebx, ebx
0x14003b35c  jz      short loc_14003B3B9
0x14003b35e  mov     al, cs:?s_isAxeMode@App@@2_NA; bool App::s_isAxeMode
0x14003b364  cmp     al, 1
0x14003b366  jnz     short loc_14003B3BF
0x14003b368  mov     [rsp+158h+arg_18], 0
0x14003b374  mov     rdx, [rsp+158h+arg_10]
0x14003b37c  lea     rcx, [rsp+158h+arg_18]
0x14003b384  call    ?attach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXPEAV?$mstring_buf@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::attach_buf(mlib::mstring_buf<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x14003b389  mov     [rsp+158h+var_128], 0
0x14003b392  mov     rdx, [rsp+158h+arg_8]
0x14003b39a  lea     rcx, [rsp+158h+var_128]
0x14003b39f  call    ?attach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXPEAV?$mstring_buf@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::attach_buf(mlib::mstring_buf<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x14003b3a4  mov     r8d, ebx
0x14003b3a7  lea     rdx, [rsp+158h+arg_18]
0x14003b3af  lea     rcx, [rsp+158h+var_128]
0x14003b3b4  call    ?WriteFailureToAxeResultsXML@@YAJV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@0H@Z; WriteFailureToAxeResultsXML(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>,int)
0x14003b3b9  mov     al, cs:?s_isAxeMode@App@@2_NA; bool App::s_isAxeMode
0x14003b3bf  test    al, al
0x14003b3c1  jnz     loc_14003B5DE
0x14003b3c7  lea     rcx, ?s_xmlTestFile@App@@2V?$CSmartPtr@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@@A; CSmartPtr<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>> App::s_xmlTestFile
0x14003b3ce  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x14003b3d3  mov     rcx, rax
0x14003b3d6  call    ?is_blank@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEBA_NXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::is_blank(void)
0x14003b3db  test    al, al
0x14003b3dd  jz      loc_14003B5DE
0x14003b3e3  cmp     cs:?s_WsSwapTest@App@@2_NA, 0; bool App::s_WsSwapTest
0x14003b3ea  jnz     loc_14003B5DE
0x14003b3f0  cmp     cs:?s_RegistryCreated@App@@2_NA, 0; bool App::s_RegistryCreated
0x14003b3f7  jz      loc_14003B5DE
0x14003b3fd  lea     r8, aWritingExitCod; "Writing exit code, cant msg and why msg"...
0x14003b404  mov     edx, 13Fh
0x14003b409  lea     rcx, aBaseWinsatExeP_0; "base\\winsat\\exe\\processwinsaterror.c"...
0x14003b410  call    Log_Text_F
0x14003b415  lea     rdx, aLastexitcode; "LastExitCode"
0x14003b41c  lea     rcx, [rsp+158h+arg_18]
0x14003b424  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x14003b429  nop
0x14003b42a  lea     r8, [rsp+158h+arg_18]
0x14003b432  mov     rdx, cs:qword_1401C6370
0x14003b439  lea     rcx, [rsp+158h+var_118]
0x14003b43e  call    ??0DWORDReg@mlib@@QEAA@AEBVRegistryBaseKey@1@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@1@_N@Z; mlib::DWORDReg::DWORDReg(mlib::RegistryBaseKey const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,bool)
0x14003b443  nop
0x14003b444  lea     rcx, [rsp+158h+arg_18]
0x14003b44c  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x14003b451  lea     rdx, aLastexitcodeca; "LastExitCodeCantMsg"
0x14003b458  lea     rcx, [rsp+158h+var_128]
0x14003b45d  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x14003b462  nop
0x14003b463  lea     r8, [rsp+158h+var_128]
0x14003b468  mov     rdx, cs:qword_1401C6370
0x14003b46f  lea     rcx, [rsp+158h+var_68]
0x14003b477  call    ??0RstringReg@mlib@@QEAA@AEBVRegistryBaseKey@1@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@1@_N@Z; mlib::RstringReg::RstringReg(mlib::RegistryBaseKey const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,bool)
0x14003b47c  nop
0x14003b47d  lea     rcx, [rsp+158h+var_128]
0x14003b482  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x14003b487  lea     rdx, aLastexitcodewh; "LastExitCodeWhyMsg"
0x14003b48e  lea     rcx, [rsp+158h+arg_18]
0x14003b496  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x14003b49b  nop
0x14003b49c  lea     r8, [rsp+158h+arg_18]
0x14003b4a4  mov     rdx, cs:qword_1401C6370
0x14003b4ab  lea     rcx, [rsp+158h+var_C8]
0x14003b4b3  call    ??0RstringReg@mlib@@QEAA@AEBVRegistryBaseKey@1@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@1@_N@Z; mlib::RstringReg::RstringReg(mlib::RegistryBaseKey const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,bool)
0x14003b4b8  nop
0x14003b4b9  lea     rcx, [rsp+158h+arg_18]
0x14003b4c1  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x14003b4c6  mov     edx, ebx
0x14003b4c8  lea     rcx, [rsp+158h+var_118]
0x14003b4cd  call    ??4DWORDReg@mlib@@QEAAAEAV01@K@Z; mlib::DWORDReg::operator=(ulong)
0x14003b4d2  lea     rdx, [rsp+158h+arg_8]
0x14003b4da  lea     rcx, [rsp+158h+var_68]
0x14003b4e2  call    ??4RstringReg@mlib@@QEAAAEAV01@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@1@@Z; mlib::RstringReg::operator=(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x14003b4e7  lea     rdx, [rsp+158h+arg_10]
0x14003b4ef  lea     rcx, [rsp+158h+var_C8]
0x14003b4f7  call    ??4RstringReg@mlib@@QEAAAEAV01@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@1@@Z; mlib::RstringReg::operator=(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x14003b4fc  lea     rcx, [rsp+158h+var_118]; this
0x14003b501  call    ?write@MRegistryRWBase@mlib@@UEAAHXZ; mlib::MRegistryRWBase::write(void)
0x14003b506  test    eax, eax
0x14003b508  jz      short loc_14003B52F
0x14003b50a  call    cs:__imp_GetLastError
0x14003b510  mov     r8d, eax
0x14003b513  mov     dword ptr [rsp+158h+var_138], ebx; char
0x14003b517  lea     r9, aCanTWriteLastE; "Can't write last exit code %u to the re"...
0x14003b51e  mov     edx, 149h
0x14003b523  lea     rcx, aBaseWinsatExeP_0; "base\\winsat\\exe\\processwinsaterror.c"...
0x14003b52a  call    Record_Win32Error_w
0x14003b52f  lea     rcx, [rsp+158h+var_68]; this
0x14003b537  call    ?write@MRegistryRWBase@mlib@@UEAAHXZ; mlib::MRegistryRWBase::write(void)
0x14003b53c  test    eax, eax
0x14003b53e  jz      short loc_14003B572
0x14003b540  mov     rax, [rsp+158h+arg_8]
0x14003b548  mov     rbx, [rax+18h]
0x14003b54c  call    cs:__imp_GetLastError
0x14003b552  mov     qword ptr [rsp+158h+var_138], rbx; char
0x14003b557  lea     r9, aCanTWriteError; "Can't write error message '%s' to the r"...
0x14003b55e  mov     r8d, eax
0x14003b561  mov     edx, 14Dh
0x14003b566  lea     rcx, aBaseWinsatExeP_0; "base\\winsat\\exe\\processwinsaterror.c"...
0x14003b56d  call    Record_Win32Error_w
0x14003b572  lea     rcx, [rsp+158h+var_C8]; this
0x14003b57a  call    ?write@MRegistryRWBase@mlib@@UEAAHXZ; mlib::MRegistryRWBase::write(void)
0x14003b57f  test    eax, eax
0x14003b581  jz      short loc_14003B5B6
0x14003b583  mov     rax, [rsp+158h+arg_10]
0x14003b58b  mov     rbx, [rax+18h]
0x14003b58f  call    cs:__imp_GetLastError
0x14003b595  mov     qword ptr [rsp+158h+var_138], rbx; char
0x14003b59a  lea     r9, aCanTWriteError; "Can't write error message '%s' to the r"...
0x14003b5a1  mov     r8d, eax
0x14003b5a4  mov     edx, 151h
0x14003b5a9  lea     rcx, aBaseWinsatExeP_0; "base\\winsat\\exe\\processwinsaterror.c"...
0x14003b5b0  call    Record_Win32Error_w
0x14003b5b5  nop
0x14003b5b6  lea     rcx, [rsp+158h+var_C8]; this
0x14003b5be  call    ??1RstringReg@mlib@@UEAA@XZ; mlib::RstringReg::~RstringReg(void)
0x14003b5c3  nop
0x14003b5c4  lea     rcx, [rsp+158h+var_68]; this
0x14003b5cc  call    ??1RstringReg@mlib@@UEAA@XZ; mlib::RstringReg::~RstringReg(void)
0x14003b5d1  nop
0x14003b5d2  lea     rcx, [rsp+158h+var_118]; this
0x14003b5d7  call    ??1DWORDReg@mlib@@UEAA@XZ; mlib::DWORDReg::~DWORDReg(void)
0x14003b5dc  jmp     short loc_14003B5F7
0x14003b5de  lea     r8, aSkippingWritin; "Skipping writing the exit code, cant ms"...
0x14003b5e5  mov     edx, 154h
0x14003b5ea  lea     rcx, aBaseWinsatExeP_0; "base\\winsat\\exe\\processwinsaterror.c"...
0x14003b5f1  call    Log_Text_F
0x14003b5f6  nop
0x14003b5f7  lea     rcx, [rsp+158h+arg_10]
0x14003b5ff  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x14003b604  nop
0x14003b605  lea     rcx, [rsp+158h+arg_8]
0x14003b60d  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
  ... truncated ...
```
