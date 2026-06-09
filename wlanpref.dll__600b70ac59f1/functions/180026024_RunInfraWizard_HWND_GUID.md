# RunInfraWizard(HWND__ *,_GUID *)

- ea: `0x180026024`
- end: `0x1800262db`
- name: `?RunInfraWizard@@YAJPEAUHWND__@@PEAU_GUID@@@Z`
- size: `695`
- prototype: `__int64 __fastcall(HWND, struct _GUID *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000fdf0`

## callees

- `0x1800012e8`
- `0x18000130c`
- `0x180003458`
- `0x18000d578`
- `0x180020800`
- `0x180023054`
- `0x180026024`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180026286`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180026286`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180026118`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180026118`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18002609a`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18002609a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RunInfraWizard(struct IUnknown *a1, struct _GUID *a2)
{
  int v3; // ebx
  HRESULT v4; // eax
  HRESULT v5; // edi
  _QWORD *v6; // rcx
  HRESULT Instance; // eax
  struct _GUID *v8; // rax
  struct _GUID *v9; // rsi
  int v10; // eax
  struct IUnknown *ppv; // [rsp+90h] [rbp+8h] BYREF

  ppv = a1;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 145) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 148) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 17), 10, WPP_f20f06ec2a2b3843231d270c9803a965_Traceguids);
  }
  ppv = 0;
  if ( !a2 )
  {
    v3 = -2147024809;
    goto LABEL_41;
  }
  v4 = CoInitializeEx(0, 6u);
  v5 = v4;
  if ( v4 >= 0 )
    goto LABEL_12;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 145)
    && (*((_BYTE *)WPP_GLOBAL_Control + 148) & 1) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 17),
      11,
      WPP_f20f06ec2a2b3843231d270c9803a965_Traceguids,
      (unsigned int)v4);
LABEL_12:
    v6 = WPP_GLOBAL_Control;
  }
  v3 = 0;
  if ( v5 != -2147417850 )
    v3 = v5;
  if ( v3 < 0 )
    goto LABEL_33;
  Instance = CoCreateInstance(&CLSID_CXWizard, 0, 0x401u, &IID_IXWizard, (LPVOID *)&ppv);
  v3 = Instance;
  if ( Instance >= 0 )
  {
    v8 = (struct _GUID *)operator new(0x10u);
    v9 = v8;
    if ( v8 )
    {
      *v8 = *a2;
      v10 = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD, _QWORD, GUID *, _DWORD, _DWORD, _QWORD, struct _GUID *, int))ppv->lpVtbl[7].AddRef)(
              ppv,
              0,
              0,
              &CLSID_InfraConnectTask,
              0,
              0,
              0,
              v8,
              1);
      v3 = v10;
      if ( v10 < 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 145)
          && (*((_BYTE *)WPP_GLOBAL_Control + 148) & 1) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 17),
            14,
            WPP_f20f06ec2a2b3843231d270c9803a965_Traceguids,
            (unsigned int)v10);
        }
        operator delete(v9);
      }
    }
    else
    {
      v3 = -2147024882;
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || !*((_BYTE *)WPP_GLOBAL_Control + 145)
        || (*((_BYTE *)WPP_GLOBAL_Control + 148) & 1) == 0 )
      {
        goto LABEL_33;
      }
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 17), 13, WPP_f20f06ec2a2b3843231d270c9803a965_Traceguids);
    }
  }
  else
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || !*((_BYTE *)WPP_GLOBAL_Control + 145)
      || (*((_BYTE *)WPP_GLOBAL_Control + 148) & 1) == 0 )
    {
      goto LABEL_33;
    }
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 17),
      12,
      WPP_f20f06ec2a2b3843231d270c9803a965_Traceguids,
      (unsigned int)Instance);
  }
  v6 = WPP_GLOBAL_Control;
LABEL_33:
  if ( ppv )
  {
    ATL::AtlComPtrAssign(&ppv, 0);
    v6 = WPP_GLOBAL_Control;
  }
  if ( v5 != -2147417850 )
  {
    CoUninitialize();
    v6 = WPP_GLOBAL_Control;
  }
  if ( v6 != &WPP_GLOBAL_Control && *((_BYTE *)v6 + 145) >= 4u && (*((_BYTE *)v6 + 148) & 1) != 0 )
    WPP_SF_(v6[17], 15, WPP_f20f06ec2a2b3843231d270c9803a965_Traceguids);
LABEL_41:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180026024  mov     [rsp+arg_0], rcx
0x180026029  push    rbx
0x18002602a  push    rbp
0x18002602b  push    rsi
0x18002602c  push    rdi
0x18002602d  push    r12
0x18002602f  push    r13
0x180026031  sub     rsp, 58h
0x180026035  mov     rbp, rdx
0x180026038  lea     r12, WPP_GLOBAL_Control
0x18002603f  lea     r13, WPP_f20f06ec2a2b3843231d270c9803a965_Traceguids
0x180026046  mov     rcx, cs:WPP_GLOBAL_Control
0x18002604d  cmp     rcx, r12
0x180026050  jz      short loc_180026078
0x180026052  cmp     byte ptr [rcx+91h], 4
0x180026059  jb      short loc_180026078
0x18002605b  test    byte ptr [rcx+94h], 1
0x180026062  jz      short loc_180026078
0x180026064  mov     edx, 0Ah
0x180026069  mov     r8, r13
0x18002606c  mov     rcx, [rcx+88h]
0x180026073  call    WPP_SF_
0x180026078  mov     [rsp+88h+arg_0], 0
0x180026084  test    rbp, rbp
0x180026087  jnz     short loc_180026093
0x180026089  mov     ebx, 80070057h
0x18002608e  jmp     loc_1800262BF
0x180026093  mov     edx, 6; dwCoInit
0x180026098  xor     ecx, ecx; pvReserved
0x18002609a  call    cs:__imp_CoInitializeEx
0x1800260a0  mov     edi, eax
0x1800260a2  test    eax, eax
0x1800260a4  jns     short loc_1800260DB
0x1800260a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800260ad  cmp     rcx, r12
0x1800260b0  jz      short loc_1800260E2
0x1800260b2  cmp     byte ptr [rcx+91h], 1
0x1800260b9  jb      short loc_1800260E2
0x1800260bb  test    byte ptr [rcx+94h], 1
0x1800260c2  jz      short loc_1800260E2
0x1800260c4  mov     edx, 0Bh
0x1800260c9  mov     r9d, eax
0x1800260cc  mov     r8, r13
0x1800260cf  mov     rcx, [rcx+88h]
0x1800260d6  call    WPP_SF_d
0x1800260db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800260e2  xor     ebx, ebx
0x1800260e4  cmp     edi, 80010106h
0x1800260ea  cmovnz  ebx, edi
0x1800260ed  test    ebx, ebx
0x1800260ef  js      loc_18002625D
0x1800260f5  lea     rax, [rsp+88h+arg_0]
0x1800260fd  mov     [rsp+88h+ppv], rax; ppv
0x180026102  lea     r9, IID_IXWizard; riid
0x180026109  xor     edx, edx; pUnkOuter
0x18002610b  mov     r8d, 401h; dwClsContext
0x180026111  lea     rcx, CLSID_CXWizard; rclsid
0x180026118  call    cs:__imp_CoCreateInstance
0x18002611e  mov     ebx, eax
0x180026120  test    eax, eax
0x180026122  jns     short loc_18002616A
0x180026124  mov     rcx, cs:WPP_GLOBAL_Control
0x18002612b  cmp     rcx, r12
0x18002612e  jz      loc_18002625D
0x180026134  cmp     byte ptr [rcx+91h], 1
0x18002613b  jb      loc_18002625D
0x180026141  test    byte ptr [rcx+94h], 1
0x180026148  jz      loc_18002625D
0x18002614e  mov     edx, 0Ch
0x180026153  mov     r9d, eax
0x180026156  mov     r8, r13
0x180026159  mov     rcx, [rcx+88h]
0x180026160  call    WPP_SF_d
0x180026165  jmp     loc_180026256
0x18002616a  mov     ecx, 10h; Size
0x18002616f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180026174  mov     rsi, rax
0x180026177  test    rax, rax
0x18002617a  jnz     short loc_1800261C2
0x18002617c  mov     ebx, 8007000Eh
0x180026181  mov     rcx, cs:WPP_GLOBAL_Control
0x180026188  cmp     rcx, r12
0x18002618b  jz      loc_18002625D
0x180026191  cmp     byte ptr [rcx+91h], 1
0x180026198  jb      loc_18002625D
0x18002619e  test    byte ptr [rcx+94h], 1
0x1800261a5  jz      loc_18002625D
0x1800261ab  lea     edx, [rax+0Dh]
0x1800261ae  mov     r8, r13
0x1800261b1  mov     rcx, [rcx+88h]
0x1800261b8  call    WPP_SF_
0x1800261bd  jmp     loc_180026256
0x1800261c2  movups  xmm0, xmmword ptr [rbp+0]
0x1800261c6  movdqu  xmmword ptr [rax], xmm0
0x1800261ca  mov     rcx, [rsp+88h+arg_0]
0x1800261d2  mov     rax, [rcx]
0x1800261d5  mov     [rsp+88h+var_48], 1
0x1800261dd  mov     [rsp+88h+var_50], rsi
0x1800261e2  mov     [rsp+88h+var_58], 0
0x1800261eb  mov     [rsp+88h+var_60], 0
0x1800261f3  mov     dword ptr [rsp+88h+ppv], 0
0x1800261fb  lea     r9, CLSID_InfraConnectTask
0x180026202  xor     r8d, r8d
0x180026205  xor     edx, edx
0x180026207  mov     rax, [rax+0B0h]
0x18002620e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026213  mov     ebx, eax
0x180026215  test    eax, eax
0x180026217  jns     short loc_180026256
0x180026219  mov     rcx, cs:WPP_GLOBAL_Control
0x180026220  cmp     rcx, r12
0x180026223  jz      short loc_18002624E
0x180026225  cmp     byte ptr [rcx+91h], 1
0x18002622c  jb      short loc_18002624E
0x18002622e  test    byte ptr [rcx+94h], 1
0x180026235  jz      short loc_18002624E
0x180026237  mov     edx, 0Eh
0x18002623c  mov     r9d, eax
0x18002623f  mov     r8, r13
0x180026242  mov     rcx, [rcx+88h]
0x180026249  call    WPP_SF_d
0x18002624e  mov     rcx, rsi; Block
0x180026251  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180026256  mov     rcx, cs:WPP_GLOBAL_Control
0x18002625d  cmp     [rsp+88h+arg_0], 0
0x180026266  jz      short loc_18002627E
0x180026268  xor     edx, edx; struct IUnknown *
0x18002626a  lea     rcx, [rsp+88h+arg_0]; struct IUnknown **
0x180026272  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180026277  mov     rcx, cs:WPP_GLOBAL_Control
0x18002627e  cmp     edi, 80010106h
0x180026284  jz      short loc_180026293
0x180026286  call    cs:__imp_CoUninitialize
0x18002628c  mov     rcx, cs:WPP_GLOBAL_Control
0x180026293  cmp     rcx, r12
0x180026296  jz      short loc_1800262BF
0x180026298  cmp     byte ptr [rcx+91h], 4
0x18002629f  jb      short loc_1800262BF
0x1800262a1  test    byte ptr [rcx+94h], 1
0x1800262a8  jz      short loc_1800262BF
0x1800262aa  mov     edx, 0Fh
0x1800262af  mov     r8, r13
0x1800262b2  mov     rcx, [rcx+88h]
0x1800262b9  call    WPP_SF_
0x1800262be  nop
0x1800262bf  lea     rcx, [rsp+88h+arg_0]
0x1800262c7  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800262cc  mov     eax, ebx
0x1800262ce  add     rsp, 58h
0x1800262d2  pop     r13
0x1800262d4  pop     r12
0x1800262d6  pop     rdi
0x1800262d7  pop     rsi
0x1800262d8  pop     rbp
0x1800262d9  pop     rbx
0x1800262da  retn
```
