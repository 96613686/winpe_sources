# CASFHeaderObjectv1::Read(ulong,uchar *,ulong *)

- ea: `0x1800136d0`
- end: `0x1800139ac`
- name: `?Read@CASFHeaderObjectv1@@UEAAJKPEAEPEAK@Z`
- size: `732`
- prototype: `__int64 __fastcall(struct IWMSCriticalSection **this, unsigned int, unsigned __int8 *, unsigned int *)`
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800015d0`
- `0x1800021dc`
- `0x18000220c`
- `0x180009dd8`
- `0x180010924`
- `0x1800111f8`
- `0x1800122b0`
- `0x1800124e0`
- `0x180012adc`
- `0x180012eb0`
- `0x1800136d0`
- `0x1800310c0`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall CASFHeaderObjectv1::Read(
        struct IWMSCriticalSection **this,
        unsigned int a2,
        unsigned __int8 *a3,
        unsigned int *a4)
{
  int fixed; // ebx
  unsigned int v9; // r14d
  __int128 v10; // xmm0
  unsigned __int64 v11; // rax
  int v12; // eax
  struct IWMSCriticalSection *v13; // rcx
  unsigned int v14; // r12d
  struct IWMSCriticalSection *v15; // rcx
  char v17[8]; // [rsp+30h] [rbp-20h] BYREF
  unsigned int v18[2]; // [rsp+38h] [rbp-18h] BYREF
  int v19; // [rsp+40h] [rbp-10h] BYREF
  int v20; // [rsp+44h] [rbp-Ch] BYREF

  CAutoCritSec::CAutoCritSec((CAutoCritSec *)v17, this[4]);
  if ( !this[5] )
  {
    fixed = -1072887818;
LABEL_32:
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v17);
    return (unsigned int)fixed;
  }
  if ( a4 )
  {
    v9 = 24;
    if ( !a2 )
      goto LABEL_30;
    if ( a3 )
    {
      if ( a2 >= 0x18 )
      {
        (*(void (__fastcall **)(struct IWMSCriticalSection *, GUID *))(*(_QWORD *)this[11] + 64LL))(
          this[11],
          &GUID_NULL);
        v10 = *(_OWORD *)a3;
        v18[0] = 24;
        *((_OWORD *)this + 3) = v10;
        v11 = *((_QWORD *)a3 + 2);
        this[8] = (struct IWMSCriticalSection *)v11;
        if ( v11 >= 0xA00000 )
        {
          fixed = -1072887821;
LABEL_31:
          *a4 = v9;
          goto LABEL_32;
        }
        v9 = *((_DWORD *)this + 16);
        if ( a2 >= v9 )
        {
          v12 = CHECK_FOR_SPACE(v18, 6u, a2);
          fixed = -1072887855;
          if ( v12 == -1072887855 )
          {
            *a4 = v18[0];
          }
          else
          {
            v13 = this[5];
            v14 = v18[0];
            *((_DWORD *)this + 91) = *((_DWORD *)a3 + 6);
            *((_BYTE *)this + 361) = a3[28];
            *((_BYTE *)this + 360) = a3[29];
            if ( v13 )
            {
              *(_QWORD *)v18 = 0;
              if ( (**(int (__fastcall ***)(struct IWMSCriticalSection *, GUID *, unsigned int *))v13)(
                     v13,
                     &IID_IASFReadWriteTracker,
                     v18) >= 0 )
              {
                (*(void (__fastcall **)(_QWORD, unsigned __int8 *, _QWORD, char *))(**(_QWORD **)v18 + 72LL))(
                  *(_QWORD *)v18,
                  a3,
                  v14,
                  (char *)this + 48);
                if ( *(_QWORD *)v18 )
                  (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v18 + 16LL))(*(_QWORD *)v18);
              }
            }
            *((GUID *)this + 3) = CLSID_ASFHeaderObject;
            v19 = 0;
            if ( v9 >= v14 )
            {
              fixed = (*(__int64 (__fastcall **)(struct IWMSCriticalSection *, struct IWMSCriticalSection *, _QWORD, unsigned __int8 *, int *))(*(_QWORD *)this[11] + 80LL))(
                        this[11],
                        this[5],
                        v9 - v14,
                        a3 + 30,
                        &v19);
              if ( fixed >= 0 )
              {
                v20 = 0;
                *a4 = v14 + v19;
                if ( (*(int (__fastcall **)(struct IWMSCriticalSection *, GUID *, int *))(*(_QWORD *)this[11] + 24LL))(
                       this[11],
                       &CLSID_ASFStreamPropertiesObject,
                       &v20) >= 0 )
                {
                  v15 = this[5];
                  *(_QWORD *)v18 = 0;
                  if ( (int)ASFGetHeaderObject(v15, &CLSID_ASFFilePropertiesObject, &IID_IASFFilePropertiesObject, v18) >= 0 )
                  {
                    (*(void (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)v18 + 272LL))(
                      *(_QWORD *)v18,
                      (unsigned __int8)v20);
                    if ( *(_QWORD *)v18 )
                      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v18 + 16LL))(*(_QWORD *)v18);
                  }
                }
                fixed = CASFHeaderObjectv1::FixContentDescription((CASFHeaderObjectv1 *)this);
                if ( fixed >= 0 )
                {
                  fixed = CASFHeaderObjectv1::FixBitrates((CASFHeaderObjectv1 *)this);
                  if ( fixed >= 0 )
                  {
                    fixed = CASFHeaderObjectv1::FixEncryptionObjects((CASFHeaderObjectv1 *)this);
                    if ( fixed >= 0 )
                    {
                      fixed = CASFHeaderObjectv1::FixStreamPropertiesObjects((CASFHeaderObjectv1 *)this);
                      if ( fixed >= 0 )
                      {
                        fixed = CASFHeaderObjectv1::FixExtendedStreamProperties((CASFHeaderObjectv1 *)this);
                        if ( fixed >= 0 )
                        {
                          fixed = CASFHeaderObjectv1::HeaderValidation((CASFHeaderObjectv1 *)this);
                          if ( fixed >= 0 )
                          {
                            CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v17);
                            return 0;
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
            else
            {
              fixed = -2147467259;
            }
          }
          goto LABEL_32;
        }
      }
LABEL_30:
      fixed = -1072887855;
      goto LABEL_31;
    }
  }
  CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v17);
  return 2147942487LL;
}

```

## disassembly

```asm
0x1800136d0  mov     [rsp-38h+arg_8], rbx
0x1800136d5  push    rbp
0x1800136d6  push    rsi
0x1800136d7  push    rdi
0x1800136d8  push    r12
0x1800136da  push    r13
0x1800136dc  push    r14
0x1800136de  push    r15
0x1800136e0  mov     rbp, rsp
0x1800136e3  sub     rsp, 50h
0x1800136e7  mov     rax, cs:__security_cookie
0x1800136ee  xor     rax, rsp
0x1800136f1  mov     [rbp+var_8], rax
0x1800136f5  mov     ebx, edx
0x1800136f7  mov     rdi, rcx
0x1800136fa  mov     rdx, [rcx+20h]; struct IWMSCriticalSection *
0x1800136fe  mov     rsi, r9
0x180013701  lea     rcx, [rbp+var_20]; this
0x180013705  mov     r15, r8
0x180013708  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x18001370d  cmp     qword ptr [rdi+28h], 0
0x180013712  jnz     short loc_18001371E
0x180013714  mov     ebx, 0C00D07F6h
0x180013719  jmp     loc_18001396D
0x18001371e  test    rsi, rsi
0x180013721  jz      loc_18001397A
0x180013727  mov     r14d, 18h
0x18001372d  test    ebx, ebx
0x18001372f  jz      loc_180013965
0x180013735  test    r15, r15
0x180013738  jz      loc_18001397A
0x18001373e  cmp     ebx, r14d
0x180013741  jb      loc_180013965
0x180013747  mov     rcx, [rdi+58h]
0x18001374b  lea     rdx, GUID_NULL
0x180013752  mov     rax, [rcx]
0x180013755  mov     rax, [rax+40h]
0x180013759  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001375e  movups  xmm0, xmmword ptr [r15]
0x180013762  lea     r13, [rdi+30h]
0x180013766  mov     [rbp+var_18], r14d
0x18001376a  movdqu  xmmword ptr [r13+0], xmm0
0x180013770  mov     rax, [r15+10h]
0x180013774  mov     [rdi+40h], rax
0x180013778  cmp     rax, 0A00000h
0x18001377e  jb      short loc_18001378A
0x180013780  mov     ebx, 0C00D07F3h
0x180013785  jmp     loc_18001396A
0x18001378a  mov     r14d, [rdi+40h]
0x18001378e  cmp     ebx, r14d
0x180013791  jb      loc_180013965
0x180013797  mov     r8d, ebx; unsigned int
0x18001379a  lea     rcx, [rbp+var_18]; unsigned int *
0x18001379e  mov     edx, 6; unsigned int
0x1800137a3  call    ?CHECK_FOR_SPACE@@YAJAEAKKK@Z; CHECK_FOR_SPACE(ulong &,ulong,ulong)
0x1800137a8  mov     ebx, 0C00D07D1h
0x1800137ad  cmp     eax, ebx
0x1800137af  jnz     short loc_1800137BB
0x1800137b1  mov     eax, [rbp+var_18]
0x1800137b4  mov     [rsi], eax
0x1800137b6  jmp     loc_18001396D
0x1800137bb  mov     eax, [r15+18h]
0x1800137bf  mov     rcx, [rdi+28h]
0x1800137c3  mov     r12d, [rbp+var_18]
0x1800137c7  mov     [rdi+16Ch], eax
0x1800137cd  mov     al, [r15+1Ch]
0x1800137d1  mov     [rdi+169h], al
0x1800137d7  mov     al, [r15+1Dh]
0x1800137db  mov     [rdi+168h], al
0x1800137e1  test    rcx, rcx
0x1800137e4  jz      short loc_180013836
0x1800137e6  mov     qword ptr [rbp+var_18], 0
0x1800137ee  lea     r8, [rbp+var_18]
0x1800137f2  mov     rax, [rcx]
0x1800137f5  lea     rdx, IID_IASFReadWriteTracker
0x1800137fc  mov     rax, [rax]
0x1800137ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013804  test    eax, eax
0x180013806  js      short loc_180013836
0x180013808  mov     rcx, qword ptr [rbp+var_18]
0x18001380c  mov     r9, r13
0x18001380f  mov     r8d, r12d
0x180013812  mov     rdx, r15
0x180013815  mov     rax, [rcx]
0x180013818  mov     rax, [rax+48h]
0x18001381c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013821  mov     rcx, qword ptr [rbp+var_18]
0x180013825  test    rcx, rcx
0x180013828  jz      short loc_180013836
0x18001382a  mov     rax, [rcx]
0x18001382d  mov     rax, [rax+10h]
0x180013831  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013836  movups  xmm0, xmmword ptr cs:CLSID_ASFHeaderObject.Data1
0x18001383d  movdqu  xmmword ptr [r13+0], xmm0
0x180013843  xor     r13d, r13d
0x180013846  mov     [rbp+var_10], r13d
0x18001384a  cmp     r14d, r12d
0x18001384d  jnb     short loc_180013859
0x18001384f  mov     ebx, 80004005h
0x180013854  jmp     loc_18001396D
0x180013859  mov     rcx, [rdi+58h]
0x18001385d  lea     rdx, [rbp+var_10]
0x180013861  mov     [rsp+50h+var_30], rdx
0x180013866  lea     r9, [r15+1Eh]
0x18001386a  mov     rdx, [rdi+28h]
0x18001386e  sub     r14d, r12d
0x180013871  mov     r8d, r14d
0x180013874  mov     rax, [rcx]
0x180013877  mov     rax, [rax+50h]
0x18001387b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013880  mov     ebx, eax
0x180013882  test    eax, eax
0x180013884  js      loc_18001396D
0x18001388a  mov     ecx, [rbp+var_10]
0x18001388d  lea     r8, [rbp+var_C]
0x180013891  add     ecx, r12d
0x180013894  mov     [rbp+var_C], r13d
0x180013898  mov     [rsi], ecx
0x18001389a  lea     rdx, CLSID_ASFStreamPropertiesObject
0x1800138a1  mov     rcx, [rdi+58h]
0x1800138a5  mov     rax, [rcx]
0x1800138a8  mov     rax, [rax+18h]
0x1800138ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800138b1  test    eax, eax
0x1800138b3  js      short loc_180013904
0x1800138b5  mov     rcx, [rdi+28h]
0x1800138b9  lea     r9, [rbp+var_18]
0x1800138bd  lea     r8, IID_IASFFilePropertiesObject
0x1800138c4  mov     qword ptr [rbp+var_18], r13
0x1800138c8  lea     rdx, CLSID_ASFFilePropertiesObject
0x1800138cf  call    ASFGetHeaderObject
0x1800138d4  test    eax, eax
0x1800138d6  js      short loc_180013904
0x1800138d8  mov     rcx, qword ptr [rbp+var_18]
0x1800138dc  movzx   edx, byte ptr [rbp+var_C]
0x1800138e0  mov     rax, [rcx]
0x1800138e3  mov     rax, [rax+110h]
0x1800138ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800138ef  mov     rcx, qword ptr [rbp+var_18]
0x1800138f3  test    rcx, rcx
0x1800138f6  jz      short loc_180013904
0x1800138f8  mov     rax, [rcx]
0x1800138fb  mov     rax, [rax+10h]
0x1800138ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013904  mov     rcx, rdi; this
0x180013907  call    ?FixContentDescription@CASFHeaderObjectv1@@IEAAJXZ; CASFHeaderObjectv1::FixContentDescription(void)
0x18001390c  mov     ebx, eax
0x18001390e  test    eax, eax
0x180013910  js      short loc_18001396D
0x180013912  mov     rcx, rdi; this
0x180013915  call    ?FixBitrates@CASFHeaderObjectv1@@IEAAJXZ; CASFHeaderObjectv1::FixBitrates(void)
0x18001391a  mov     ebx, eax
0x18001391c  test    eax, eax
0x18001391e  js      short loc_18001396D
0x180013920  mov     rcx, rdi; this
0x180013923  call    ?FixEncryptionObjects@CASFHeaderObjectv1@@IEAAJXZ; CASFHeaderObjectv1::FixEncryptionObjects(void)
0x180013928  mov     ebx, eax
0x18001392a  test    eax, eax
0x18001392c  js      short loc_18001396D
0x18001392e  mov     rcx, rdi; this
0x180013931  call    ?FixStreamPropertiesObjects@CASFHeaderObjectv1@@IEAAJXZ; CASFHeaderObjectv1::FixStreamPropertiesObjects(void)
0x180013936  mov     ebx, eax
0x180013938  test    eax, eax
0x18001393a  js      short loc_18001396D
0x18001393c  mov     rcx, rdi; this
0x18001393f  call    ?FixExtendedStreamProperties@CASFHeaderObjectv1@@IEAAJXZ; CASFHeaderObjectv1::FixExtendedStreamProperties(void)
0x180013944  mov     ebx, eax
0x180013946  test    eax, eax
0x180013948  js      short loc_18001396D
0x18001394a  mov     rcx, rdi; this
0x18001394d  call    ?HeaderValidation@CASFHeaderObjectv1@@IEAAJXZ; CASFHeaderObjectv1::HeaderValidation(void)
0x180013952  mov     ebx, eax
0x180013954  test    eax, eax
0x180013956  js      short loc_18001396D
0x180013958  lea     rcx, [rbp+var_20]; this
0x18001395c  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x180013961  xor     eax, eax
0x180013963  jmp     short loc_180013988
0x180013965  mov     ebx, 0C00D07D1h
0x18001396a  mov     [rsi], r14d
0x18001396d  lea     rcx, [rbp+var_20]; this
0x180013971  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x180013976  mov     eax, ebx
0x180013978  jmp     short loc_180013988
0x18001397a  lea     rcx, [rbp+var_20]; this
0x18001397e  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x180013983  mov     eax, 80070057h
0x180013988  mov     rcx, [rbp+var_8]
0x18001398c  xor     rcx, rsp; StackCookie
0x18001398f  call    __security_check_cookie
0x180013994  mov     rbx, [rsp+50h+arg_8]
0x18001399c  add     rsp, 50h
0x1800139a0  pop     r15
0x1800139a2  pop     r14
0x1800139a4  pop     r13
0x1800139a6  pop     r12
0x1800139a8  pop     rdi
0x1800139a9  pop     rsi
0x1800139aa  pop     rbp
0x1800139ab  retn
```
