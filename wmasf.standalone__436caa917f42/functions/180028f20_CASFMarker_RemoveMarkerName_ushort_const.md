# CASFMarker::RemoveMarkerName(ushort const *)

- ea: `0x180028f20`
- end: `0x180029063`
- name: `?RemoveMarkerName@CASFMarker@@UEAAJPEBG@Z`
- size: `323`
- prototype: `__int64 __fastcall(CASFMarker *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x1800011c0`
- `0x1800015d0`
- `0x1800021dc`
- `0x18000220c`
- `0x180027e50`
- `0x180028ebc`
- `0x180028f20`
- `0x180030a00`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall CASFMarker::RemoveMarkerName(struct IWMSCriticalSection **this, const unsigned __int16 *a2)
{
  struct IWMSCriticalSection *v4; // rcx
  int i; // ebx
  int v6; // ebx
  unsigned int v7; // edi
  _WORD *v8; // rax
  __int64 v9; // rax
  _BYTE v11[8]; // [rsp+20h] [rbp-40h] BYREF
  _BYTE v12[16]; // [rsp+28h] [rbp-38h] BYREF
  _BYTE v13[16]; // [rsp+38h] [rbp-28h] BYREF
  __int64 v14; // [rsp+48h] [rbp-18h] BYREF
  unsigned __int16 v15; // [rsp+50h] [rbp-10h] BYREF

  CAutoCritSec::CAutoCritSec((CAutoCritSec *)v11, this[2]);
  v4 = this[4];
  if ( v4 )
  {
    v14 = 0;
    i = ASFFindHeaderObject(v4, &CLSID_ASFLanguageListObject, &IID_IASFLanguageListObject, &v14);
    if ( i >= 0 )
    {
      v15 = 0;
      v6 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, unsigned __int16 *))(*(_QWORD *)v14 + 120LL))(
             v14,
             a2,
             &v15);
      if ( v14 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
        v14 = 0;
      }
      if ( v6 >= 0 )
      {
        v7 = 0;
        for ( i = -1072887824; v7 < *((_DWORD *)this + 164); ++v7 )
        {
          v8 = (_WORD *)CTDynArray<CASFMarker::MARKER_NAME_REC,20>::operator[](this + 34, v12, v7);
          if ( v15 == *v8 )
          {
            v9 = CTDynArray<CASFMarker::MARKER_NAME_REC,20>::operator[](this + 34, v13, v7);
            operator delete(*(void **)(v9 + 8));
            CTDynArray<CASFMarker::MARKER_NAME_REC,20>::RemoveAt(this + 34, v15);
            i = 0;
          }
        }
      }
      else
      {
        i = -1072887854;
      }
    }
  }
  else
  {
    i = -1072887818;
  }
  CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v11);
  return (unsigned int)i;
}

```

## disassembly

```asm
0x180028f20  mov     [rsp-18h+arg_10], rbx
0x180028f25  mov     [rsp-18h+arg_18], rsi
0x180028f2a  push    rbp
0x180028f2b  push    rdi
0x180028f2c  push    r14
0x180028f2e  mov     rbp, rsp
0x180028f31  sub     rsp, 60h
0x180028f35  mov     rax, cs:__security_cookie
0x180028f3c  xor     rax, rsp
0x180028f3f  mov     [rbp+var_8], rax
0x180028f43  mov     rdi, rdx
0x180028f46  mov     rsi, rcx
0x180028f49  mov     rdx, [rcx+10h]; struct IWMSCriticalSection *
0x180028f4d  lea     rcx, [rbp+var_40]; this
0x180028f51  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x180028f56  mov     rcx, [rsi+20h]
0x180028f5a  test    rcx, rcx
0x180028f5d  jnz     short loc_180028F69
0x180028f5f  mov     ebx, 0C00D07F6h
0x180028f64  jmp     loc_180029037
0x180028f69  lea     r9, [rbp+var_18]
0x180028f6d  mov     [rbp+var_18], 0
0x180028f75  lea     r8, IID_IASFLanguageListObject
0x180028f7c  lea     rdx, CLSID_ASFLanguageListObject
0x180028f83  call    ASFFindHeaderObject
0x180028f88  mov     ebx, eax
0x180028f8a  test    eax, eax
0x180028f8c  js      loc_180029037
0x180028f92  mov     rcx, [rbp+var_18]
0x180028f96  lea     r8, [rbp+var_10]
0x180028f9a  xor     eax, eax
0x180028f9c  mov     rdx, rdi
0x180028f9f  mov     [rbp+var_10], ax
0x180028fa3  mov     rax, [rcx]
0x180028fa6  mov     rax, [rax+78h]
0x180028faa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028faf  mov     rcx, [rbp+var_18]
0x180028fb3  mov     ebx, eax
0x180028fb5  test    rcx, rcx
0x180028fb8  jz      short loc_180028FCE
0x180028fba  mov     rdx, [rcx]
0x180028fbd  mov     rax, [rdx+10h]
0x180028fc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028fc6  mov     [rbp+var_18], 0
0x180028fce  test    ebx, ebx
0x180028fd0  jns     short loc_180028FD9
0x180028fd2  mov     ebx, 0C00D07D2h
0x180028fd7  jmp     short loc_180029037
0x180028fd9  xor     edi, edi
0x180028fdb  mov     ebx, 0C00D07F0h
0x180028fe0  cmp     [rsi+290h], edi
0x180028fe6  jbe     short loc_180029037
0x180028fe8  lea     r14, [rsi+110h]
0x180028fef  mov     r8d, edi
0x180028ff2  lea     rdx, [rbp+var_38]
0x180028ff6  mov     rcx, r14
0x180028ff9  call    ??A?$CTDynArray@UMARKER_NAME_REC@CASFMarker@@$0BE@@@QEBA?AUMARKER_NAME_REC@CASFMarker@@K@Z; CTDynArray<CASFMarker::MARKER_NAME_REC,20>::operator[](ulong)
0x180028ffe  movzx   ecx, word ptr [rax]
0x180029001  cmp     [rbp+var_10], cx
0x180029005  jnz     short loc_18002902D
0x180029007  mov     r8d, edi
0x18002900a  lea     rdx, [rbp+var_28]
0x18002900e  mov     rcx, r14
0x180029011  call    ??A?$CTDynArray@UMARKER_NAME_REC@CASFMarker@@$0BE@@@QEBA?AUMARKER_NAME_REC@CASFMarker@@K@Z; CTDynArray<CASFMarker::MARKER_NAME_REC,20>::operator[](ulong)
0x180029016  mov     rcx, [rax+8]; Block
0x18002901a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002901f  movzx   edx, [rbp+var_10]
0x180029023  mov     rcx, r14
0x180029026  call    ?RemoveAt@?$CTDynArray@UMARKER_NAME_REC@CASFMarker@@$0BE@@@QEAAHKK@Z; CTDynArray<CASFMarker::MARKER_NAME_REC,20>::RemoveAt(ulong,ulong)
0x18002902b  xor     ebx, ebx
0x18002902d  inc     edi
0x18002902f  cmp     edi, [rsi+290h]
0x180029035  jb      short loc_180028FEF
0x180029037  lea     rcx, [rbp+var_40]; this
0x18002903b  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x180029040  mov     eax, ebx
0x180029042  mov     rcx, [rbp+var_8]
0x180029046  xor     rcx, rsp; StackCookie
0x180029049  call    __security_check_cookie
0x18002904e  lea     r11, [rsp+60h+var_s0]
0x180029053  mov     rbx, [r11+30h]
0x180029057  mov     rsi, [r11+38h]
0x18002905b  mov     rsp, r11
0x18002905e  pop     r14
0x180029060  pop     rdi
0x180029061  pop     rbp
0x180029062  retn
```
