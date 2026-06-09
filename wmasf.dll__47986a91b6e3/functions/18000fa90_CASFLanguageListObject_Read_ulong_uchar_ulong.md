# CASFLanguageListObject::Read(ulong,uchar *,ulong *)

- ea: `0x18000fa90`
- end: `0x18000fd12`
- name: `?Read@CASFLanguageListObject@@UEAAJKPEAEPEAK@Z`
- size: `642`
- prototype: `__int64 __fastcall(CASFLanguageListObject *__hidden this, unsigned int, unsigned __int8 *, unsigned int *)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops`

## callees

- `0x1800011c0`
- `0x1800011cc`
- `0x1800015d0`
- `0x1800021dc`
- `0x18000220c`
- `0x180009dd8`
- `0x18000c334`
- `0x18000fa90`
- `0x18003f2a0`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall CASFLanguageListObject::Read(
        CASFLanguageListObject *this,
        unsigned int a2,
        unsigned __int8 *a3,
        unsigned int *a4)
{
  unsigned __int64 v4; // rbx
  unsigned int v8; // ebx
  unsigned __int64 v9; // rcx
  bool v10; // cf
  unsigned int v11; // eax
  unsigned __int16 v12; // ax
  unsigned __int8 *v13; // r13
  unsigned __int16 v14; // r12
  unsigned int v15; // r8d
  size_t v16; // rdx
  unsigned __int8 v17; // r10
  void *v18; // r15
  char *v19; // rax
  size_t v20; // r13
  int (__fastcall ***v21)(_QWORD, GUID *, unsigned int *); // rcx
  unsigned __int16 v23; // [rsp+30h] [rbp-40h]
  char v24[8]; // [rsp+38h] [rbp-38h] BYREF
  size_t Size; // [rsp+40h] [rbp-30h]
  unsigned __int64 v26; // [rsp+48h] [rbp-28h]
  char *v27; // [rsp+50h] [rbp-20h]
  unsigned int v28[2]; // [rsp+58h] [rbp-18h] BYREF

  v4 = a2;
  CAutoCritSec::CAutoCritSec((CAutoCritSec *)v24, *((struct IWMSCriticalSection **)this + 4));
  if ( !*((_QWORD *)this + 5) )
  {
    v8 = -1072887818;
LABEL_31:
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v24);
    return v8;
  }
  if ( !a4 )
    goto LABEL_32;
  if ( !(_DWORD)v4 )
  {
LABEL_30:
    *a4 = 26;
    v8 = -1072887855;
    goto LABEL_31;
  }
  if ( !a3 )
  {
LABEL_32:
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v24);
    return 2147942487LL;
  }
  if ( (unsigned int)v4 < 0x1A )
    goto LABEL_30;
  (*(void (__fastcall **)(CASFLanguageListObject *))(*(_QWORD *)this + 144LL))(this);
  *((_OWORD *)this + 3) = *(_OWORD *)a3;
  v9 = *((_QWORD *)a3 + 2);
  *((_QWORD *)this + 8) = v9;
  if ( v9 >= 0x100000000LL )
  {
    v8 = -1072887821;
    goto LABEL_31;
  }
  v10 = v4 < v9;
  v8 = -1072887855;
  if ( v10 )
  {
    v11 = *((_DWORD *)this + 16);
LABEL_11:
    *a4 = v11;
    goto LABEL_31;
  }
  v12 = *((_WORD *)a3 + 12);
  v13 = a3 + 26;
  v14 = 0;
  v23 = v12;
  v28[0] = 26;
  while ( v14 < v12 )
  {
    if ( (unsigned int)CHECK_FOR_SPACE(v28, 1u, *((_DWORD *)this + 16)) == -1072887855
      || (unsigned int)CHECK_FOR_SPACE(v28, *v13, v15) == -1072887855 )
    {
      v11 = v28[0];
      goto LABEL_11;
    }
    if ( ((unsigned __int8)v16 & v17) != 0 || !(_BYTE)v16 )
    {
      v8 = -1072887838;
      *a4 = v28[0];
      goto LABEL_31;
    }
    Size = v16;
    v26 = (unsigned __int64)(unsigned int)v16 >> 1;
    v18 = operator new[](saturated_mul(v26, 2u));
    if ( !v18 )
      goto LABEL_22;
    v19 = (char *)(v13 + 1);
    v20 = Size;
    v27 = v19;
    memcpy_0(v18, v19, Size);
    *((_WORD *)v18 + v26 - 1) = 0;
    if ( !(unsigned int)CTDynArray<unsigned short *,20>::Add((char *)this + 88, v18, 0) )
    {
      operator delete(v18);
LABEL_22:
      v8 = -2147024882;
      goto LABEL_31;
    }
    v13 = (unsigned __int8 *)&v27[v20];
    v12 = v23;
    ++v14;
  }
  *a4 = v28[0];
  v21 = (int (__fastcall ***)(_QWORD, GUID *, unsigned int *))*((_QWORD *)this + 5);
  if ( v21 )
  {
    *(_QWORD *)v28 = 0;
    if ( (**v21)(v21, &IID_IASFReadWriteTracker, v28) >= 0 )
    {
      (*(void (__fastcall **)(_QWORD, unsigned __int8 *, _QWORD, char *))(**(_QWORD **)v28 + 72LL))(
        *(_QWORD *)v28,
        a3,
        *a4,
        (char *)this + 48);
      if ( *(_QWORD *)v28 )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v28 + 16LL))(*(_QWORD *)v28);
    }
  }
  CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v24);
  return 0;
}

```

## disassembly

```asm
0x18000fa90  mov     [rsp-38h+arg_8], rbx
0x18000fa95  push    rbp
0x18000fa96  push    rsi
0x18000fa97  push    rdi
0x18000fa98  push    r12
0x18000fa9a  push    r13
0x18000fa9c  push    r14
0x18000fa9e  push    r15
0x18000faa0  mov     rbp, rsp
0x18000faa3  sub     rsp, 70h
0x18000faa7  mov     rax, cs:__security_cookie
0x18000faae  xor     rax, rsp
0x18000fab1  mov     [rbp+var_10], rax
0x18000fab5  mov     ebx, edx
0x18000fab7  mov     rsi, rcx
0x18000faba  mov     rdx, [rcx+20h]; struct IWMSCriticalSection *
0x18000fabe  mov     rdi, r9
0x18000fac1  lea     rcx, [rbp+var_38]; this
0x18000fac5  mov     r14, r8
0x18000fac8  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x18000facd  cmp     qword ptr [rsi+28h], 0
0x18000fad2  jnz     short loc_18000FADE
0x18000fad4  mov     ebx, 0C00D07F6h
0x18000fad9  jmp     loc_18000FCD3
0x18000fade  test    rdi, rdi
0x18000fae1  jz      loc_18000FCE0
0x18000fae7  mov     r15d, 1Ah
0x18000faed  test    ebx, ebx
0x18000faef  jz      loc_18000FCCB
0x18000faf5  test    r14, r14
0x18000faf8  jz      loc_18000FCE0
0x18000fafe  cmp     ebx, r15d
0x18000fb01  jb      loc_18000FCCB
0x18000fb07  mov     rax, [rsi]
0x18000fb0a  mov     rcx, rsi
0x18000fb0d  mov     rax, [rax+90h]
0x18000fb14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fb19  movups  xmm0, xmmword ptr [r14]
0x18000fb1d  mov     rax, 100000000h
0x18000fb27  movdqu  xmmword ptr [rsi+30h], xmm0
0x18000fb2c  mov     rcx, [r14+10h]
0x18000fb30  mov     [rsi+40h], rcx
0x18000fb34  cmp     rcx, rax
0x18000fb37  jb      short loc_18000FB43
0x18000fb39  mov     ebx, 0C00D07F3h
0x18000fb3e  jmp     loc_18000FCD3
0x18000fb43  cmp     rbx, rcx
0x18000fb46  mov     ebx, 0C00D07D1h
0x18000fb4b  jnb     short loc_18000FB57
0x18000fb4d  mov     eax, [rsi+40h]
0x18000fb50  mov     [rdi], eax
0x18000fb52  jmp     loc_18000FCD3
0x18000fb57  movzx   eax, word ptr [r14+18h]
0x18000fb5c  lea     r13, [r14+1Ah]
0x18000fb60  xor     r12d, r12d
0x18000fb63  mov     [rbp+var_40], ax
0x18000fb67  mov     [rbp+var_18], r15d
0x18000fb6b  lea     r10d, [r12+1]
0x18000fb70  cmp     r12w, ax
0x18000fb74  jnb     loc_18000FC5F
0x18000fb7a  mov     r8d, [rsi+40h]; unsigned int
0x18000fb7e  lea     rcx, [rbp+var_18]; unsigned int *
0x18000fb82  mov     edx, r10d; unsigned int
0x18000fb85  call    ?CHECK_FOR_SPACE@@YAJAEAKKK@Z; CHECK_FOR_SPACE(ulong &,ulong,ulong)
0x18000fb8a  cmp     eax, ebx
0x18000fb8c  jz      loc_18000FC57
0x18000fb92  movzx   edx, byte ptr [r13+0]; unsigned int
0x18000fb97  lea     rcx, [rbp+var_18]; unsigned int *
0x18000fb9b  call    ?CHECK_FOR_SPACE@@YAJAEAKKK@Z; CHECK_FOR_SPACE(ulong &,ulong,ulong)
0x18000fba0  cmp     eax, ebx
0x18000fba2  jz      loc_18000FC57
0x18000fba8  test    r10b, dl
0x18000fbab  jnz     loc_18000FC4B
0x18000fbb1  test    dl, dl
0x18000fbb3  jz      loc_18000FC4B
0x18000fbb9  mov     ecx, edx
0x18000fbbb  mov     [rbp+Size], rdx
0x18000fbbf  shr     rcx, 1
0x18000fbc2  mov     eax, 2
0x18000fbc7  mul     rcx
0x18000fbca  mov     [rbp+var_28], rcx
0x18000fbce  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000fbd5  cmovb   rax, rcx
0x18000fbd9  mov     rcx, rax; unsigned __int64
0x18000fbdc  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000fbe1  mov     r15, rax
0x18000fbe4  test    rax, rax
0x18000fbe7  jz      short loc_18000FC41
0x18000fbe9  lea     rax, [r13+1]
0x18000fbed  mov     rcx, r15; void *
0x18000fbf0  mov     r13, [rbp+Size]
0x18000fbf4  mov     rdx, rax; Src
0x18000fbf7  mov     r8, r13; Size
0x18000fbfa  mov     [rbp+var_20], rax
0x18000fbfe  call    memcpy_0
0x18000fc03  mov     rcx, [rbp+var_28]
0x18000fc07  xor     eax, eax
0x18000fc09  xor     r8d, r8d
0x18000fc0c  mov     rdx, r15
0x18000fc0f  mov     [r15+rcx*2-2], ax
0x18000fc15  lea     rcx, [rsi+58h]
0x18000fc19  call    ?Add@?$CTDynArray@PEAG$0BE@@@QEAAHPEAGPEAK@Z; CTDynArray<ushort *,20>::Add(ushort *,ulong *)
0x18000fc1e  test    eax, eax
0x18000fc20  jz      short loc_18000FC39
0x18000fc22  add     r13, [rbp+var_20]
0x18000fc26  mov     r10d, 1
0x18000fc2c  movzx   eax, [rbp+var_40]
0x18000fc30  add     r12w, r10w
0x18000fc34  jmp     loc_18000FB70
0x18000fc39  mov     rcx, r15; Block
0x18000fc3c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000fc41  mov     ebx, 8007000Eh
0x18000fc46  jmp     loc_18000FCD3
0x18000fc4b  mov     eax, [rbp+var_18]
0x18000fc4e  mov     ebx, 0C00D07E2h
0x18000fc53  mov     [rdi], eax
0x18000fc55  jmp     short loc_18000FCD3
0x18000fc57  mov     eax, [rbp+var_18]
0x18000fc5a  jmp     loc_18000FB50
0x18000fc5f  mov     eax, [rbp+var_18]
0x18000fc62  mov     [rdi], eax
0x18000fc64  mov     rcx, [rsi+28h]
0x18000fc68  test    rcx, rcx
0x18000fc6b  jz      short loc_18000FCBE
0x18000fc6d  mov     qword ptr [rbp+var_18], 0
0x18000fc75  lea     r8, [rbp+var_18]
0x18000fc79  mov     rax, [rcx]
0x18000fc7c  lea     rdx, IID_IASFReadWriteTracker
0x18000fc83  mov     rax, [rax]
0x18000fc86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fc8b  test    eax, eax
0x18000fc8d  js      short loc_18000FCBE
0x18000fc8f  mov     rcx, qword ptr [rbp+var_18]
0x18000fc93  lea     r9, [rsi+30h]
0x18000fc97  mov     r8d, [rdi]
0x18000fc9a  mov     rdx, r14
0x18000fc9d  mov     rax, [rcx]
0x18000fca0  mov     rax, [rax+48h]
0x18000fca4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fca9  mov     rcx, qword ptr [rbp+var_18]
0x18000fcad  test    rcx, rcx
0x18000fcb0  jz      short loc_18000FCBE
0x18000fcb2  mov     rax, [rcx]
0x18000fcb5  mov     rax, [rax+10h]
0x18000fcb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fcbe  lea     rcx, [rbp+var_38]; this
0x18000fcc2  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x18000fcc7  xor     eax, eax
0x18000fcc9  jmp     short loc_18000FCEE
0x18000fccb  mov     [rdi], r15d
0x18000fcce  mov     ebx, 0C00D07D1h
0x18000fcd3  lea     rcx, [rbp+var_38]; this
0x18000fcd7  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x18000fcdc  mov     eax, ebx
0x18000fcde  jmp     short loc_18000FCEE
0x18000fce0  lea     rcx, [rbp+var_38]; this
0x18000fce4  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x18000fce9  mov     eax, 80070057h
0x18000fcee  mov     rcx, [rbp+var_10]
0x18000fcf2  xor     rcx, rsp; StackCookie
0x18000fcf5  call    __security_check_cookie
0x18000fcfa  mov     rbx, [rsp+70h+arg_8]
0x18000fd02  add     rsp, 70h
0x18000fd06  pop     r15
0x18000fd08  pop     r14
0x18000fd0a  pop     r13
0x18000fd0c  pop     r12
0x18000fd0e  pop     rdi
0x18000fd0f  pop     rsi
0x18000fd10  pop     rbp
0x18000fd11  retn
```
