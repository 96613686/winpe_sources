# CASFIndexObjectv2::Write(ulong,uchar *,ulong *)

- ea: `0x180005fd0`
- end: `0x1800061e9`
- name: `?Write@CASFIndexObjectv2@@UEAAJKPEAEPEAK@Z`
- size: `537`
- prototype: `__int64 __fastcall(struct IWMSCriticalSection **this, unsigned int, unsigned __int8 *, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800015d0`
- `0x1800021dc`
- `0x18000220c`
- `0x180005fd0`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall CASFIndexObjectv2::Write(
        struct IWMSCriticalSection **this,
        unsigned int a2,
        unsigned __int8 *a3,
        unsigned int *a4)
{
  int v8; // ebx
  struct IWMSCriticalSection *v9; // rax
  unsigned int v10; // eax
  unsigned int v12; // r9d
  unsigned __int8 *v13; // r10
  int v14; // eax
  char *i; // r8
  unsigned int v16; // edx
  struct IWMSCriticalSection *v17; // rcx
  char v18[8]; // [rsp+30h] [rbp-48h] BYREF
  __int64 v19; // [rsp+38h] [rbp-40h] BYREF
  unsigned __int64 v20; // [rsp+40h] [rbp-38h] BYREF

  CAutoCritSec::CAutoCritSec((CAutoCritSec *)v18, this[4]);
  if ( !this[5] )
  {
    v8 = -1072887818;
LABEL_11:
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v18);
    return (unsigned int)v8;
  }
  if ( a4 && (!a2 || a3) )
  {
    v9 = *this;
    v20 = 0;
    v8 = (*((__int64 (__fastcall **)(struct IWMSCriticalSection **, unsigned __int64 *, _QWORD))v9 + 7))(this, &v20, 0);
    if ( v8 < 0 )
      goto LABEL_11;
    v10 = v20;
    if ( v20 >= 0x100000000LL )
    {
      v8 = -1072887821;
      goto LABEL_11;
    }
    *a4 = v20;
    if ( a2 < v10 )
    {
      v8 = -1072887855;
      goto LABEL_11;
    }
    v12 = 0;
    v13 = a3 + 34;
    *(_OWORD *)a3 = *((_OWORD *)this + 3);
    *((_QWORD *)a3 + 2) = this[8];
    *((_DWORD *)a3 + 6) = *((_DWORD *)this + 112);
    *((_WORD *)a3 + 14) = *((_WORD *)this + 220);
    for ( *(_DWORD *)(a3 + 30) = *((_DWORD *)this + 113); v12 < *((_DWORD *)this + 110); v13 += 4 )
    {
      v14 = 0;
      if ( v12 < *((_DWORD *)this + 110) )
      {
        for ( i = (char *)(this + 39); i; i = (char *)*((_QWORD *)i + 13) )
        {
          v16 = *((_DWORD *)i + 2);
          if ( v12 >= v16 && v12 < v16 + 20 )
          {
            if ( ((unsigned __int8)i[((unsigned __int64)(v12 - v16) >> 3) + 20]
                & *((_BYTE *)&CTSparseBlock<unsigned long,CASFIndexObjectv2::INDEX_SPECIFIER,20,0>::s_bSingleBitMasks
                  + (((_BYTE)v12 - (_BYTE)v16) & 7))) != 0 )
            {
              v14 = *(_DWORD *)&i[4 * (v12 - v16) + 24];
              goto LABEL_23;
            }
            break;
          }
        }
        if ( (*((_BYTE *)this + 324) & 1) != 0 )
          v14 = *((_DWORD *)this + 82);
      }
LABEL_23:
      *(_DWORD *)v13 = v14;
      ++v12;
    }
    v17 = this[5];
    if ( v17 )
    {
      v19 = 0;
      if ( (**(int (__fastcall ***)(struct IWMSCriticalSection *, GUID *, __int64 *))v17)(
             v17,
             &IID_IASFReadWriteTracker,
             &v19) >= 0 )
      {
        (*(void (__fastcall **)(__int64, unsigned __int8 *, _QWORD, char *))(*(_QWORD *)v19 + 80LL))(
          v19,
          a3,
          *a4,
          (char *)this + 48);
        if ( v19 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
      }
    }
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v18);
    return 0;
  }
  else
  {
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v18);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180005fd0  mov     [rsp+arg_8], rbx
0x180005fd5  push    rbp
0x180005fd6  push    rsi
0x180005fd7  push    rdi
0x180005fd8  push    r14
0x180005fda  push    r15
0x180005fdc  sub     rsp, 50h
0x180005fe0  mov     rax, cs:__security_cookie
0x180005fe7  xor     rax, rsp
0x180005fea  mov     [rsp+78h+var_30], rax
0x180005fef  mov     esi, edx
0x180005ff1  mov     rdi, rcx
0x180005ff4  mov     rdx, [rcx+20h]; struct IWMSCriticalSection *
0x180005ff8  mov     r14, r9
0x180005ffb  lea     rcx, [rsp+78h+var_48]; this
0x180006000  mov     rbp, r8
0x180006003  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x180006008  cmp     qword ptr [rdi+28h], 0
0x18000600d  jnz     short loc_180006016
0x18000600f  mov     ebx, 0C00D07F6h
0x180006014  jmp     short loc_180006079
0x180006016  test    r14, r14
0x180006019  jz      loc_1800061B9
0x18000601f  test    esi, esi
0x180006021  jz      short loc_18000602C
0x180006023  test    rbp, rbp
0x180006026  jz      loc_1800061B9
0x18000602c  mov     rax, [rdi]
0x18000602f  lea     rdx, [rsp+78h+var_38]
0x180006034  xor     r8d, r8d
0x180006037  mov     [rsp+78h+var_38], 0
0x180006040  mov     rcx, rdi
0x180006043  mov     rax, [rax+38h]
0x180006047  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000604c  mov     ebx, eax
0x18000604e  test    eax, eax
0x180006050  js      short loc_180006079
0x180006052  mov     rax, [rsp+78h+var_38]
0x180006057  mov     rcx, 100000000h
0x180006061  cmp     rax, rcx
0x180006064  jb      short loc_18000606D
0x180006066  mov     ebx, 0C00D07F3h
0x18000606b  jmp     short loc_180006079
0x18000606d  mov     [r14], eax
0x180006070  cmp     esi, eax
0x180006072  jnb     short loc_18000608A
0x180006074  mov     ebx, 0C00D07D1h
0x180006079  lea     rcx, [rsp+78h+var_48]; this
0x18000607e  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x180006083  mov     eax, ebx
0x180006085  jmp     loc_1800061C8
0x18000608a  movups  xmm0, xmmword ptr [rdi+30h]
0x18000608e  xor     r9d, r9d
0x180006091  lea     r10, [rbp+22h]
0x180006095  movdqu  xmmword ptr [rbp+0], xmm0
0x18000609a  mov     rax, [rdi+40h]
0x18000609e  mov     [rbp+10h], rax
0x1800060a2  mov     eax, [rdi+1C0h]
0x1800060a8  mov     [rbp+18h], eax
0x1800060ab  movzx   eax, word ptr [rdi+1B8h]
0x1800060b2  mov     [rbp+1Ch], ax
0x1800060b6  mov     eax, [rdi+1C4h]
0x1800060bc  mov     [rbp+1Eh], eax
0x1800060bf  cmp     [rdi+1B8h], r9d
0x1800060c6  jbe     loc_18000614D
0x1800060cc  lea     r11, [rdi+138h]
0x1800060d3  xor     eax, eax
0x1800060d5  cmp     r9d, [r11+80h]
0x1800060dc  jnb     short loc_180006131
0x1800060de  mov     r8, r11
0x1800060e1  test    r8, r8
0x1800060e4  jz      short loc_180006126
0x1800060e6  mov     edx, [r8+8]
0x1800060ea  cmp     r9d, edx
0x1800060ed  jb      short loc_1800060F7
0x1800060ef  lea     ecx, [rdx+14h]
0x1800060f2  cmp     r9d, ecx
0x1800060f5  jb      short loc_1800060FD
0x1800060f7  mov     r8, [r8+68h]
0x1800060fb  jmp     short loc_1800060E1
0x1800060fd  mov     ecx, r9d
0x180006100  lea     r15, ?s_bSingleBitMasks@?$CTSparseBlock@KUINDEX_SPECIFIER@CASFIndexObjectv2@@$0BE@$0A@@@0PAEA; uchar near * CTSparseBlock<ulong,CASFIndexObjectv2::INDEX_SPECIFIER,20,0>::s_bSingleBitMasks
0x180006107  sub     ecx, edx
0x180006109  mov     ebx, ecx
0x18000610b  mov     edx, ebx
0x18000610d  shr     rcx, 3
0x180006111  and     edx, 7
0x180006114  mov     cl, [rcx+r8+14h]
0x180006119  test    [rdx+r15], cl
0x18000611d  jz      short loc_180006126
0x18000611f  mov     eax, [r8+rbx*4+18h]
0x180006124  jmp     short loc_180006131
0x180006126  test    byte ptr [r11+0Ch], 1
0x18000612b  jz      short loc_180006131
0x18000612d  mov     eax, [r11+10h]
0x180006131  mov     [r10], ax
0x180006135  inc     r9d
0x180006138  shr     eax, 10h
0x18000613b  mov     [r10+2], ax
0x180006140  add     r10, 4
0x180006144  cmp     r9d, [rdi+1B8h]
0x18000614b  jb      short loc_1800060D3
0x18000614d  mov     rcx, [rdi+28h]
0x180006151  test    rcx, rcx
0x180006154  jz      short loc_1800061AB
0x180006156  mov     [rsp+78h+var_40], 0
0x18000615f  lea     r8, [rsp+78h+var_40]
0x180006164  mov     rax, [rcx]
0x180006167  lea     rdx, IID_IASFReadWriteTracker
0x18000616e  mov     rax, [rax]
0x180006171  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006176  test    eax, eax
0x180006178  js      short loc_1800061AB
0x18000617a  mov     rcx, [rsp+78h+var_40]
0x18000617f  lea     r9, [rdi+30h]
0x180006183  mov     r8d, [r14]
0x180006186  mov     rdx, rbp
0x180006189  mov     rax, [rcx]
0x18000618c  mov     rax, [rax+50h]
0x180006190  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006195  mov     rcx, [rsp+78h+var_40]
0x18000619a  test    rcx, rcx
0x18000619d  jz      short loc_1800061AB
0x18000619f  mov     rax, [rcx]
0x1800061a2  mov     rax, [rax+10h]
0x1800061a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800061ab  lea     rcx, [rsp+78h+var_48]; this
0x1800061b0  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x1800061b5  xor     eax, eax
0x1800061b7  jmp     short loc_1800061C8
0x1800061b9  lea     rcx, [rsp+78h+var_48]; this
0x1800061be  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x1800061c3  mov     eax, 80070057h
0x1800061c8  mov     rcx, [rsp+78h+var_30]
0x1800061cd  xor     rcx, rsp; StackCookie
0x1800061d0  call    __security_check_cookie
0x1800061d5  mov     rbx, [rsp+78h+arg_8]
0x1800061dd  add     rsp, 50h
0x1800061e1  pop     r15
0x1800061e3  pop     r14
0x1800061e5  pop     rdi
0x1800061e6  pop     rsi
0x1800061e7  pop     rbp
0x1800061e8  retn
```
