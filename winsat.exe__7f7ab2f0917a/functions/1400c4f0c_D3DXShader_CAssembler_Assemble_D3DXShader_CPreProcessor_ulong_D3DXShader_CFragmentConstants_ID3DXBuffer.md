# D3DXShader::CAssembler::Assemble(D3DXShader::CPreProcessor *,ulong,D3DXShader::CFragmentConstants *,ID3DXBuffer * *)

- ea: `0x1400c4f0c`
- end: `0x1400c5529`
- name: `?Assemble@CAssembler@D3DXShader@@QEAAJPEAVCPreProcessor@2@KPEAVCFragmentConstants@2@PEAPEAUID3DXBuffer@@@Z`
- size: `1565`
- prototype: `__int64 __fastcall(D3DXShader::CAssembler *this, struct D3DXShader::CPreProcessor *, int, struct D3DXShader::CFragmentConstants *, struct ID3DXBuffer **)`
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, loader_planting`

## callers

- `0x14009a75c`

## callees

- `0x140001abc`
- `0x140003560`
- `0x14008c0e0`
- `0x140096034`
- `0x140097c44`
- `0x140097fa8`
- `0x1400a96b4`
- `0x1400aaba4`
- `0x1400aafa0`
- `0x1400c4ac4`
- `0x1400c4c68`
- `0x1400c4e1c`
- `0x1400c4f0c`
- `0x1400c6aa4`
- `0x1400c6ae8`
- `0x1400c6ed0`
- `0x1400c8c8c`
- `0x1400c8dc8`
- `0x1400c8f84`
- `0x14011a010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1400c534d`
- `KERNEL32!GetProcAddress` at `0x1400c534d`
- `KERNEL32!LoadLibraryA` at `0x1400c5338`
- `KERNEL32!LoadLibraryA` at `0x1400c5338`
- `KERNEL32!GetModuleHandleA` at `0x1400c5326`
- `KERNEL32!GetModuleHandleA` at `0x1400c5326`

## string_xrefs

- `0x1400c531f`: `d3d9.dll`
- `0x1400c5331`: `d3d9.dll`
- `0x1400c5343`: `Direct3DShaderValidatorCreate9`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall D3DXShader::CAssembler::Assemble(
        D3DXShader::CAssembler *this,
        struct D3DXShader::CPreProcessor *a2,
        int a3,
        struct D3DXShader::CFragmentConstants *a4,
        struct ID3DXBuffer **a5)
{
  void *v9; // rcx
  unsigned int v10; // edx
  D3DXShader::CFragmentInfo *v11; // rcx
  _DWORD *v12; // rbp
  _DWORD *v13; // r13
  __int64 v14; // rax
  __int64 result; // rax
  _DWORD *v16; // r15
  unsigned int *v17; // rsi
  __int64 v18; // rcx
  __int64 v19; // rdx
  int v20; // ebx
  __int64 v21; // rcx
  int v22; // eax
  D3DXShader::CFragmentInfo *v23; // rax
  __int64 v24; // rax
  unsigned int v25; // eax
  int v26; // ecx
  HMODULE ModuleHandleA; // rax
  __int64 (*ProcAddress)(void); // rax
  __int64 v29; // rax
  D3DXShader *v30; // rcx
  D3DXShader::CPreProcessor *v31; // rcx
  __int64 v32; // rcx
  unsigned int v33; // ecx
  struct ID3DXBuffer *v34; // rsi
  unsigned int v35; // eax
  const void *v36; // rdi
  unsigned int v37; // ebx
  void *v38; // rax
  struct D3DXCore::CBuffer *v39[2]; // [rsp+30h] [rbp-58h] BYREF

  if ( (a3 & 0xFFFFFF3C) != 0 || !a5 )
    return 2289436780LL;
  v9 = (void *)*((_QWORD *)this + 15);
  *a5 = 0;
  operator delete(v9);
  v11 = (D3DXShader::CFragmentInfo *)*((_QWORD *)this + 21);
  if ( v11 )
    D3DXShader::CFragmentInfo::`scalar deleting destructor'(v11, v10);
  *((_QWORD *)this + 1) = a2;
  *(_QWORD *)this = (char *)a2 + 32;
  v12 = (_DWORD *)((char *)this + 144);
  *((_QWORD *)this + 18) = 0;
  v13 = (_DWORD *)((char *)this + 152);
  *((_DWORD *)this + 38) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 15) = 0;
  *((_QWORD *)this + 16) = 0;
  *((_QWORD *)this + 17) = 0;
  *(_QWORD *)((char *)this + 108) = 0;
  *((_DWORD *)this + 29) = 0;
  *((_DWORD *)this + 23) = a3;
  *((_DWORD *)this + 22) = -1;
  *((_QWORD *)this + 20) = 0;
  *((_QWORD *)this + 21) = 0;
  v14 = *((_QWORD *)a2 + 148);
  D3DXShader::CAssembler::s_pAsm = this;
  if ( !*(_QWORD *)(v14 + 32) )
    D3DXShader::CPreProcessor::GetBufferPointer(a2, (const char **)this + 18, (unsigned int *)this + 38);
  result = D3DXShader::CPreProcessor::Begin(*((D3DXShader::CPreProcessor **)this + 1), 2u);
  if ( (int)result >= 0 )
  {
    D3DXShader::CAssembler::Token(this);
    v16 = (_DWORD *)((char *)this + 24);
    v17 = (unsigned int *)((char *)this + 32);
    if ( *((_DWORD *)this + 6) == 9 )
    {
      v18 = *(_QWORD *)v17;
      *(_OWORD *)v39 = 0;
      if ( (int)D3DXGetTargetDescByName(v18, 1, v39) >= 0 )
      {
        *v17 = (unsigned int)v39[1];
        *v16 = 0;
        goto LABEL_11;
      }
    }
    else if ( !*v16 )
    {
LABEL_11:
      v19 = *((unsigned int *)this + 8);
      switch ( (_DWORD)v19 )
      {
        case 0xFFFE0100:
          D3DXShader::CTErrors::Warning(
            *(D3DXShader::CTErrors **)this,
            (D3DXShader::CAssembler *)((char *)this + 24),
            0x7DFu,
            "vs_1_0 is no longer supported; using vs_1_1");
          v19 = 4294836481LL;
          *v17 = -130815;
          break;
        case 0xFFFF0100:
          D3DXShader::CTErrors::Warning(
            *(D3DXShader::CTErrors **)this,
            (D3DXShader::CAssembler *)((char *)this + 24),
            0x7DFu,
            "ps_1_0 is no longer supported; using ps_1_1");
          v19 = 4294902017LL;
          *v17 = -65279;
          break;
        case 0xFFFF0202:
          *v17 = -65023;
          v19 = 4294902273LL;
          break;
      }
      v22 = v19 & 0xFFFF0000;
      if ( (a3 & 0x40) != 0 && v22 == -131072 || v22 == -65536 && (a3 & 0x80u) != 0 )
        *((_DWORD *)this + 23) |= 1u;
      if ( (unsigned int)v19 > 0xFFFF0102 )
      {
        switch ( (_DWORD)v19 )
        {
          case 0xFFFF0103:
            *((_DWORD *)this + 22) = 8;
            break;
          case 0xFFFF0104:
            *((_DWORD *)this + 22) = 9;
            break;
          case 0xFFFF0200:
            *((_DWORD *)this + 22) = 10;
            break;
          case 0xFFFF0201:
            *((_DWORD *)this + 22) = 11;
            break;
          case 0xFFFF02FF:
            *((_DWORD *)this + 22) = 12;
            break;
          case 0xFFFF0300:
            *((_DWORD *)this + 22) = 13;
            break;
          case 0xFFFF03FF:
            *((_DWORD *)this + 22) = 14;
            break;
          default:
LABEL_52:
            D3DXShader::CTErrors::Error(
              *(D3DXShader::CTErrors **)this,
              (D3DXShader::CAssembler *)((char *)this + 24),
              0x7D2u,
              "unrecognized shader version");
            goto LABEL_15;
        }
      }
      else
      {
        switch ( (_DWORD)v19 )
        {
          case 0xFFFF0102:
            *((_DWORD *)this + 22) = 7;
            break;
          case 0xFFFE0101:
            *((_DWORD *)this + 22) = 0;
            break;
          case 0xFFFE0200:
            *((_DWORD *)this + 22) = 1;
            break;
          case 0xFFFE0201:
            *((_DWORD *)this + 22) = 2;
            break;
          case 0xFFFE02FF:
            *((_DWORD *)this + 22) = 3;
            break;
          case 0xFFFE0300:
            *((_DWORD *)this + 22) = 4;
            break;
          case 0xFFFE03FF:
            *((_DWORD *)this + 22) = 5;
            break;
          case 0xFFFF0101:
            *((_DWORD *)this + 22) = 6;
            break;
          default:
            goto LABEL_52;
        }
      }
      if ( !a4 )
        goto LABEL_71;
      *((_DWORD *)this + 23) |= 2u;
      *((_QWORD *)this + 22) = a4;
      v23 = (D3DXShader::CFragmentInfo *)operator new(0x148u, (const struct D3DX9MEMORY::CD3DXNEW *)v19);
      a4 = 0;
      if ( v23 )
      {
        v24 = D3DXShader::CFragmentInfo::CFragmentInfo(v23, *((_DWORD *)this + 22));
        *((_QWORD *)this + 21) = v24;
        if ( v24 )
        {
          v25 = *((_DWORD *)this + 22);
          if ( v25 > 5 )
          {
            if ( v25 - 10 > 4 )
            {
              D3DXShader::CTErrors::Error(
                *(D3DXShader::CTErrors **)this,
                (D3DXShader::CAssembler *)((char *)this + 24),
                0x7D1u,
                "only vs_1_1, vs_2_0, vs_2_x, vs_2_sw, ps_2_0, ps_2_x, and ps_2_sw are supported for assembly fragments");
              goto LABEL_71;
            }
            v26 = *((unsigned __int8 *)this + 33) | 0x7FFF00;
          }
          else
          {
            v26 = *((unsigned __int8 *)this + 33) | 0x7FFE00;
          }
          *v17 = *(unsigned __int8 *)v17 | (v26 << 8);
LABEL_71:
          if ( (*((_BYTE *)this + 92) & 2) != 0
            || (ModuleHandleA = GetModuleHandleA("d3d9.dll")) == 0 && (ModuleHandleA = LoadLibraryA("d3d9.dll")) == 0
            || (ProcAddress = GetProcAddress(ModuleHandleA, "Direct3DShaderValidatorCreate9")) == 0
            || (v29 = ProcAddress(), (*((_QWORD *)this + 2) = v29) == 0)
            || (v20 = (*(__int64 (__fastcall **)(__int64, __int64 (__fastcall *)(const char *, unsigned int, unsigned int, unsigned int, const char *, void *), D3DXShader::CAssembler *, _QWORD))(*(_QWORD *)v29 + 24LL))(
                        v29,
                        D3DXShader::CAssembler::ValidationError,
                        this,
                        0),
                v20 >= 0) )
          {
            v20 = D3DXShader::CAssembler::Emit(this, *v17);
            if ( v20 >= 0 )
            {
              v20 = D3DXShader::CAssembler::Validate(this, (D3DXShader::CAssembler *)((char *)this + 24));
              if ( v20 >= 0 )
              {
                if ( *((_DWORD *)this + 27) != (_DWORD)a4 )
                  goto LABEL_83;
                if ( (unsigned int)D3DXShader::d3dxasm_parse(v30) )
                  *((_DWORD *)this + 27) = 1;
                if ( *((_DWORD *)this + 27) != (_DWORD)a4 )
                  goto LABEL_83;
                if ( *(struct D3DXShader::CFragmentConstants **)v12 != a4 )
                {
                  v31 = (D3DXShader::CPreProcessor *)*((_QWORD *)this + 1);
                  v39[0] = a4;
                  D3DXShader::CPreProcessor::GetBufferPointer(v31, (const char **)v39, 0);
                  if ( (struct D3DXCore::CBuffer *)*(_QWORD *)v12 < v39[0]
                    && (struct D3DXCore::CBuffer *)(*(_QWORD *)v12 + (unsigned int)*v13) > v39[0] )
                  {
                    *v13 = LODWORD(v39[0]) - *v12;
                  }
                }
                if ( *((struct D3DXShader::CFragmentConstants **)this + 21) != a4 )
                {
                  v20 = D3DXShader::CAssembler::EmitFragmentInfo(this);
                  if ( v20 < 0 )
                    goto LABEL_16;
                }
                if ( (*((_BYTE *)this + 92) & 1) != 0 )
                {
                  v20 = D3DXShader::CAssembler::EmitDebugInfo(this);
                  if ( v20 < 0 )
                    goto LABEL_16;
                }
                v20 = D3DXShader::CAssembler::Emit(this, 0xFFFFu);
                if ( v20 < 0 )
                  goto LABEL_16;
                v20 = D3DXShader::CAssembler::Validate(this, (D3DXShader::CAssembler *)((char *)this + 24));
                if ( v20 < 0 )
                  goto LABEL_16;
                v32 = *((_QWORD *)this + 2);
                if ( v32 )
                {
                  v20 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v32 + 40LL))(v32);
                  if ( v20 < 0 )
                    goto LABEL_16;
                }
                if ( *(_DWORD *)(*(_QWORD *)this + 12LL) == (_DWORD)a4 )
                {
                  v33 = 4 * *((_DWORD *)this + 32);
                  v39[0] = a4;
                  v20 = D3DXCore::CBuffer::Create(v33, v39);
                  if ( v20 >= 0 )
                  {
                    v34 = v39[0];
                    v35 = (*(__int64 (__fastcall **)(struct D3DXCore::CBuffer *))(*(_QWORD *)v39[0] + 32LL))(v39[0]);
                    v36 = (const void *)*((_QWORD *)this + 15);
                    v37 = v35;
                    v38 = (void *)(*(__int64 (__fastcall **)(struct ID3DXBuffer *))(*(_QWORD *)v34 + 24LL))(v34);
                    memcpy_0(v38, v36, v37);
                    v20 = (int)a4;
                    *a5 = v34;
                    goto LABEL_17;
                  }
                }
                else
                {
LABEL_83:
                  v20 = -2005529767;
                }
              }
            }
          }
LABEL_16:
          *((_DWORD *)this + 27) = 1;
LABEL_17:
          v21 = *((_QWORD *)this + 2);
          if ( v21 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
            *((_QWORD *)this + 2) = a4;
          }
          D3DXShader::CPreProcessor::End(*((D3DXShader::CPreProcessor **)this + 1));
          return (unsigned int)v20;
        }
      }
      else
      {
        *((_QWORD *)this + 21) = 0;
      }
      return 2147942414LL;
    }
    D3DXShader::CTErrors::Error(
      *(D3DXShader::CTErrors **)this,
      (D3DXShader::CAssembler *)((char *)this + 24),
      0x7D1u,
      "shader version expected");
LABEL_15:
    a4 = 0;
    v20 = -2005529767;
    goto LABEL_16;
  }
  return result;
}

```

## disassembly

```asm
0x1400c4f0c  push    rbx
0x1400c4f0e  push    rbp
0x1400c4f0f  push    rsi
0x1400c4f10  push    rdi
0x1400c4f11  push    r12
0x1400c4f13  push    r13
0x1400c4f15  push    r14
0x1400c4f17  push    r15
0x1400c4f19  sub     rsp, 48h
0x1400c4f1d  mov     r12, r9
0x1400c4f20  mov     edi, r8d
0x1400c4f23  mov     rbx, rdx
0x1400c4f26  mov     r14, rcx
0x1400c4f29  test    r8d, 0FFFFFF3Ch
0x1400c4f30  jnz     loc_1400C5513
0x1400c4f36  mov     rax, [rsp+88h+arg_20]
0x1400c4f3e  xor     esi, esi
0x1400c4f40  test    rax, rax
0x1400c4f43  jz      loc_1400C5513
0x1400c4f49  mov     rcx, [rcx+78h]; Block
0x1400c4f4d  mov     [rax], rsi
0x1400c4f50  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400c4f55  mov     rcx, [r14+0A8h]; this
0x1400c4f5c  test    rcx, rcx
0x1400c4f5f  jz      short loc_1400C4F66
0x1400c4f61  call    ??_GCFragmentInfo@D3DXShader@@QEAAPEAXI@Z; D3DXShader::CFragmentInfo::`scalar deleting destructor'(uint)
0x1400c4f66  lea     rax, [rbx+20h]
0x1400c4f6a  mov     [r14+8], rbx
0x1400c4f6e  mov     [r14], rax
0x1400c4f71  lea     rbp, [r14+90h]
0x1400c4f78  mov     [rbp+0], rsi
0x1400c4f7c  lea     r13, [r14+98h]
0x1400c4f83  mov     [r13+0], esi
0x1400c4f87  mov     [r14+10h], rsi
0x1400c4f8b  mov     [r14+48h], rsi
0x1400c4f8f  mov     [r14+50h], rsi
0x1400c4f93  mov     [r14+78h], rsi
0x1400c4f97  mov     [r14+80h], rsi
0x1400c4f9e  mov     [r14+88h], rsi
0x1400c4fa5  mov     [r14+6Ch], rsi
0x1400c4fa9  mov     [r14+74h], esi
0x1400c4fad  mov     [r14+5Ch], edi
0x1400c4fb1  mov     dword ptr [r14+58h], 0FFFFFFFFh
0x1400c4fb9  mov     [r14+0A0h], rsi
0x1400c4fc0  mov     [r14+0A8h], rsi
0x1400c4fc7  mov     rax, [rbx+4A0h]
0x1400c4fce  mov     cs:?s_pAsm@CAssembler@D3DXShader@@1PEAV12@EA, r14; D3DXShader::CAssembler * D3DXShader::CAssembler::s_pAsm
0x1400c4fd5  cmp     [rax+20h], rsi
0x1400c4fd9  jnz     short loc_1400C4FE9
0x1400c4fdb  mov     r8, r13; unsigned int *
0x1400c4fde  mov     rdx, rbp; char **
0x1400c4fe1  mov     rcx, rbx; this
0x1400c4fe4  call    ?GetBufferPointer@CPreProcessor@D3DXShader@@QEAAJPEAPEBDPEAI@Z; D3DXShader::CPreProcessor::GetBufferPointer(char const * *,uint *)
0x1400c4fe9  mov     rcx, [r14+8]; this
0x1400c4fed  mov     edx, 2; unsigned int
0x1400c4ff2  call    ?Begin@CPreProcessor@D3DXShader@@QEAAJK@Z; D3DXShader::CPreProcessor::Begin(ulong)
0x1400c4ff7  test    eax, eax
0x1400c4ff9  js      loc_1400C5518
0x1400c4fff  mov     rcx, r14; this
0x1400c5002  call    ?Token@CAssembler@D3DXShader@@IEAAHXZ; D3DXShader::CAssembler::Token(void)
0x1400c5007  lea     r15, [r14+18h]
0x1400c500b  cmp     dword ptr [r15], 9
0x1400c500f  lea     rsi, [r14+20h]
0x1400c5013  jnz     short loc_1400C5079
0x1400c5015  mov     rcx, [rsi]
0x1400c5018  lea     r8, [rsp+88h+var_58]
0x1400c501d  xorps   xmm0, xmm0
0x1400c5020  mov     edx, 1
0x1400c5025  movups  xmmword ptr [rsp+88h+var_58], xmm0
0x1400c502a  call    D3DXGetTargetDescByName
0x1400c502f  test    eax, eax
0x1400c5031  js      short loc_1400C507F
0x1400c5033  mov     eax, dword ptr [rsp+88h+var_58+8]
0x1400c5037  mov     [rsi], eax
0x1400c5039  mov     dword ptr [r15], 0
0x1400c5040  mov     edx, [r15+8]
0x1400c5044  mov     ebx, 0FFFF0201h
0x1400c5049  cmp     edx, 0FFFE0100h
0x1400c504f  jnz     short loc_1400C50D0
0x1400c5051  mov     rcx, [r14]; this
0x1400c5054  lea     r9, aVs10IsNoLonger; "vs_1_0 is no longer supported; using vs"...
0x1400c505b  mov     r8d, 7DFh; unsigned int
0x1400c5061  mov     rdx, r15; struct D3DXShader::D3DXTOKEN *
0x1400c5064  call    ?Warning@CTErrors@D3DXShader@@QEAAJPEAUD3DXTOKEN@2@IPEBDZZ; D3DXShader::CTErrors::Warning(D3DXShader::D3DXTOKEN *,uint,char const *,...)
0x1400c5069  mov     edx, 0FFFE0101h
0x1400c506e  mov     dword ptr [rsi], 0FFFE0101h
0x1400c5074  jmp     loc_1400C5109
0x1400c5079  cmp     dword ptr [r15], 0
0x1400c507d  jz      short loc_1400C5040
0x1400c507f  lea     r9, aShaderVersionE; "shader version expected"
0x1400c5086  mov     r8d, 7D1h; unsigned int
0x1400c508c  mov     rcx, [r14]; this
0x1400c508f  mov     rdx, r15; struct D3DXShader::D3DXTOKEN *
0x1400c5092  call    ?Error@CTErrors@D3DXShader@@QEAAJPEAUD3DXTOKEN@2@IPEBDZZ; D3DXShader::CTErrors::Error(D3DXShader::D3DXTOKEN *,uint,char const *,...)
0x1400c5097  xor     r12d, r12d
0x1400c509a  mov     ebx, 88760B59h
0x1400c509f  mov     dword ptr [r14+6Ch], 1
0x1400c50a7  mov     rcx, [r14+10h]
0x1400c50ab  test    rcx, rcx
0x1400c50ae  jz      short loc_1400C50C0
0x1400c50b0  mov     rax, [rcx]
0x1400c50b3  mov     rax, [rax+10h]
0x1400c50b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400c50bc  mov     [r14+10h], r12
0x1400c50c0  mov     rcx, [r14+8]; this
0x1400c50c4  call    ?End@CPreProcessor@D3DXShader@@QEAAJXZ; D3DXShader::CPreProcessor::End(void)
0x1400c50c9  mov     eax, ebx
0x1400c50cb  jmp     loc_1400C5518
0x1400c50d0  cmp     edx, 0FFFF0100h
0x1400c50d6  jnz     short loc_1400C50FD
0x1400c50d8  mov     rcx, [r14]; this
0x1400c50db  lea     r9, aPs10IsNoLonger; "ps_1_0 is no longer supported; using ps"...
0x1400c50e2  mov     r8d, 7DFh; unsigned int
0x1400c50e8  mov     rdx, r15; struct D3DXShader::D3DXTOKEN *
0x1400c50eb  call    ?Warning@CTErrors@D3DXShader@@QEAAJPEAUD3DXTOKEN@2@IPEBDZZ; D3DXShader::CTErrors::Warning(D3DXShader::D3DXTOKEN *,uint,char const *,...)
0x1400c50f0  mov     edx, 0FFFF0101h
0x1400c50f5  mov     dword ptr [rsi], 0FFFF0101h
0x1400c50fb  jmp     short loc_1400C5109
0x1400c50fd  cmp     edx, 0FFFF0202h
0x1400c5103  jnz     short loc_1400C5109
0x1400c5105  mov     [rsi], ebx
0x1400c5107  mov     edx, ebx; struct D3DX9MEMORY::CD3DXNEW *
0x1400c5109  mov     eax, edx
0x1400c510b  mov     ecx, 0FFFF0000h
0x1400c5110  and     eax, ecx
0x1400c5112  test    dil, 40h
0x1400c5116  jz      short loc_1400C511F
0x1400c5118  cmp     eax, 0FFFE0000h
0x1400c511d  jz      short loc_1400C512F
0x1400c511f  cmp     eax, ecx
0x1400c5121  setz    cl
0x1400c5124  test    dil, 80h
0x1400c5128  setnz   al
0x1400c512b  test    al, cl
0x1400c512d  jz      short loc_1400C5134
0x1400c512f  or      dword ptr [r14+5Ch], 1
0x1400c5134  mov     eax, 0FFFF0102h
0x1400c5139  cmp     edx, eax
0x1400c513b  ja      loc_1400C51EF
0x1400c5141  jz      loc_1400C51E2
0x1400c5147  cmp     edx, 0FFFE0101h
0x1400c514d  jz      loc_1400C51D5
0x1400c5153  cmp     edx, 0FFFE0200h
0x1400c5159  jz      short loc_1400C51C8
0x1400c515b  cmp     edx, 0FFFE0201h
0x1400c5161  jz      short loc_1400C51BB
0x1400c5163  cmp     edx, 0FFFE02FFh
0x1400c5169  jz      short loc_1400C51AE
0x1400c516b  cmp     edx, 0FFFE0300h
0x1400c5171  jz      short loc_1400C51A1
0x1400c5173  cmp     edx, 0FFFE03FFh
0x1400c5179  jz      short loc_1400C5194
0x1400c517b  cmp     edx, 0FFFF0101h
0x1400c5181  jnz     loc_1400C5223
0x1400c5187  mov     dword ptr [r14+58h], 6
0x1400c518f  jmp     loc_1400C5279
0x1400c5194  mov     dword ptr [r14+58h], 5
0x1400c519c  jmp     loc_1400C5279
0x1400c51a1  mov     dword ptr [r14+58h], 4
0x1400c51a9  jmp     loc_1400C5279
0x1400c51ae  mov     dword ptr [r14+58h], 3
0x1400c51b6  jmp     loc_1400C5279
0x1400c51bb  mov     dword ptr [r14+58h], 2
0x1400c51c3  jmp     loc_1400C5279
0x1400c51c8  mov     dword ptr [r14+58h], 1
0x1400c51d0  jmp     loc_1400C5279
0x1400c51d5  mov     dword ptr [r14+58h], 0
0x1400c51dd  jmp     loc_1400C5279
0x1400c51e2  mov     dword ptr [r14+58h], 7
0x1400c51ea  jmp     loc_1400C5279
0x1400c51ef  cmp     edx, 0FFFF0103h
0x1400c51f5  jz      short loc_1400C5271
0x1400c51f7  cmp     edx, 0FFFF0104h
0x1400c51fd  jz      short loc_1400C5267
0x1400c51ff  cmp     edx, 0FFFF0200h
0x1400c5205  jz      short loc_1400C525D
0x1400c5207  cmp     edx, ebx
0x1400c5209  jz      short loc_1400C5253
0x1400c520b  cmp     edx, 0FFFF02FFh
0x1400c5211  jz      short loc_1400C5249
0x1400c5213  cmp     edx, 0FFFF0300h
0x1400c5219  jz      short loc_1400C523F
0x1400c521b  cmp     edx, 0FFFF03FFh
0x1400c5221  jz      short loc_1400C5235
0x1400c5223  lea     r9, aUnrecognizedSh; "unrecognized shader version"
0x1400c522a  mov     r8d, 7D2h
0x1400c5230  jmp     loc_1400C508C
0x1400c5235  mov     dword ptr [r14+58h], 0Eh
0x1400c523d  jmp     short loc_1400C5279
0x1400c523f  mov     dword ptr [r14+58h], 0Dh
0x1400c5247  jmp     short loc_1400C5279
0x1400c5249  mov     dword ptr [r14+58h], 0Ch
0x1400c5251  jmp     short loc_1400C5279
0x1400c5253  mov     dword ptr [r14+58h], 0Bh
0x1400c525b  jmp     short loc_1400C5279
0x1400c525d  mov     dword ptr [r14+58h], 0Ah
0x1400c5265  jmp     short loc_1400C5279
0x1400c5267  mov     dword ptr [r14+58h], 9
0x1400c526f  jmp     short loc_1400C5279
0x1400c5271  mov     dword ptr [r14+58h], 8
0x1400c5279  test    r12, r12
0x1400c527c  jz      loc_1400C5318
0x1400c5282  or      dword ptr [r14+5Ch], 2
0x1400c5287  mov     ecx, 148h; unsigned __int64
0x1400c528c  mov     [r14+0B0h], r12
0x1400c5293  call    ??2@YAPEAX_KAEBVCD3DXNEW@D3DX9MEMORY@@@Z; operator new(unsigned __int64,D3DX9MEMORY::CD3DXNEW const &)
0x1400c5298  xor     r12d, r12d
0x1400c529b  test    rax, rax
0x1400c529e  jz      short loc_1400C5307
0x1400c52a0  mov     edx, [r14+58h]; int
0x1400c52a4  mov     rcx, rax; this
0x1400c52a7  call    ??0CFragmentInfo@D3DXShader@@QEAA@H@Z; D3DXShader::CFragmentInfo::CFragmentInfo(int)
0x1400c52ac  mov     [r14+0A8h], rax
0x1400c52b3  test    rax, rax
0x1400c52b6  jz      short loc_1400C530E
0x1400c52b8  mov     eax, [r14+58h]
0x1400c52bc  cmp     eax, 5
0x1400c52bf  ja      short loc_1400C52CE
0x1400c52c1  movzx   ecx, byte ptr [r14+21h]
0x1400c52c6  or      ecx, 7FFE00h
0x1400c52cc  jmp     short loc_1400C52E1
0x1400c52ce  add     eax, 0FFFFFFF6h
0x1400c52d1  cmp     eax, 4
0x1400c52d4  ja      short loc_1400C52ED
0x1400c52d6  movzx   ecx, byte ptr [r14+21h]
0x1400c52db  or      ecx, 7FFF00h
0x1400c52e1  movzx   eax, byte ptr [rsi]
0x1400c52e4  shl     ecx, 8
0x1400c52e7  or      ecx, eax
0x1400c52e9  mov     [rsi], ecx
0x1400c52eb  jmp     short loc_1400C5318
0x1400c52ed  mov     rcx, [r14]; this
0x1400c52f0  lea     r9, aOnlyVs11Vs20Vs; "only vs_1_1, vs_2_0, vs_2_x, vs_2_sw, p"...
0x1400c52f7  mov     r8d, 7D1h; unsigned int
0x1400c52fd  mov     rdx, r15; struct D3DXShader::D3DXTOKEN *
0x1400c5300  call    ?Error@CTErrors@D3DXShader@@QEAAJPEAUD3DXTOKEN@2@IPEBDZZ; D3DXShader::CTErrors::Error(D3DXShader::D3DXTOKEN *,uint,char const *,...)
0x1400c5305  jmp     short loc_1400C5318
0x1400c5307  mov     [r14+0A8h], r12
0x1400c530e  mov     eax, 8007000Eh
0x1400c5313  jmp     loc_1400C5518
0x1400c5318  test    byte ptr [r14+5Ch], 2
0x1400c531d  jnz     short loc_1400C538F
0x1400c531f  lea     rcx, aD3d9Dll; "d3d9.dll"
0x1400c5326  call    cs:__imp_GetModuleHandleA
0x1400c532c  test    rax, rax
0x1400c532f  jnz     short loc_1400C5343
0x1400c5331  lea     rcx, aD3d9Dll; "d3d9.dll"
0x1400c5338  call    cs:__imp_LoadLibraryA
0x1400c533e  test    rax, rax
0x1400c5341  jz      short loc_1400C538F
0x1400c5343  lea     rdx, aDirect3dshader; "Direct3DShaderValidatorCreate9"
0x1400c534a  mov     rcx, rax; hModule
0x1400c534d  call    cs:__imp_GetProcAddress
0x1400c5353  test    rax, rax
0x1400c5356  jz      short loc_1400C538F
0x1400c5358  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400c535d  mov     [r14+10h], rax
0x1400c5361  mov     r10, rax
0x1400c5364  test    rax, rax
0x1400c5367  jz      short loc_1400C538F
0x1400c5369  mov     rcx, [rax]
0x1400c536c  lea     rdx, ?ValidationError@CAssembler@D3DXShader@@KAJPEBDIKI0PEAX@Z; D3DXShader::CAssembler::ValidationError(char const *,uint,ulong,uint,char const *,void *)
0x1400c5373  xor     r9d, r9d
0x1400c5376  mov     r8, r14
0x1400c5379  mov     rax, [rcx+18h]
0x1400c537d  mov     rcx, r10
0x1400c5380  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400c5385  mov     ebx, eax
0x1400c5387  test    eax, eax
0x1400c5389  js      loc_1400C509F
0x1400c538f  mov     edx, [rsi]; unsigned int
0x1400c5391  mov     rcx, r14; this
0x1400c5394  call    ?Emit@CAssembler@D3DXShader@@IEAAJK@Z; D3DXShader::CAssembler::Emit(ulong)
0x1400c5399  mov     ebx, eax
0x1400c539b  test    eax, eax
0x1400c539d  js      loc_1400C509F
0x1400c53a3  mov     rdx, r15; struct D3DXShader::D3DXTOKEN *
0x1400c53a6  mov     rcx, r14; this
0x1400c53a9  call    ?Validate@CAssembler@D3DXShader@@IEAAJPEAUD3DXTOKEN@2@@Z; D3DXShader::CAssembler::Validate(D3DXShader::D3DXTOKEN *)
0x1400c53ae  mov     ebx, eax
0x1400c53b0  test    eax, eax
0x1400c53b2  js      loc_1400C509F
0x1400c53b8  cmp     [r14+6Ch], r12d
0x1400c53bc  jnz     short loc_1400C53D5
0x1400c53be  call    ?d3dxasm_parse@D3DXShader@@YAHXZ; D3DXShader::d3dxasm_parse(void)
0x1400c53c3  test    eax, eax
0x1400c53c5  jz      short loc_1400C53CF
0x1400c53c7  mov     dword ptr [r14+6Ch], 1
0x1400c53cf  cmp     [r14+6Ch], r12d
0x1400c53d3  jz      short loc_1400C53DF
0x1400c53d5  mov     ebx, 88760B59h
0x1400c53da  jmp     loc_1400C509F
0x1400c53df  cmp     [rbp+0], r12
0x1400c53e3  jz      short loc_1400C541A
0x1400c53e5  mov     rcx, [r14+8]; this
0x1400c53e9  lea     rdx, [rsp+88h+var_58]; char **
0x1400c53ee  xor     r8d, r8d; unsigned int *
0x1400c53f1  mov     [rsp+88h+var_58], r12
0x1400c53f6  call    ?GetBufferPointer@CPreProcessor@D3DXShader@@QEAAJPEAPEBDPEAI@Z; D3DXShader::CPreProcessor::GetBufferPointer(char const * *,uint *)
0x1400c53fb  mov     rcx, [rsp+88h+var_58]
  ... truncated ...
```
