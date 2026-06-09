# CSpp::_BuildOneVolumeProp(ushort const *,_SPP_ONDISK_VOLUME_PROP *)

- ea: `0x180011fb0`
- end: `0x180012124`
- name: `?_BuildOneVolumeProp@CSpp@@AEAAJPEBGPEAU_SPP_ONDISK_VOLUME_PROP@@@Z`
- size: `372`
- prototype: `__int64 __fastcall(CSpp *this, const unsigned __int16 *, struct _SPP_ONDISK_VOLUME_PROP *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001212c`

## callees

- `0x180011fb0`
- `0x180021120`
- `0x1800268b4`
- `0x1800269ac`
- `0x180028b7c`
- `0x18002a08c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800120ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800120ea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012103`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800120ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800120ea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012103`

## pseudocode

```c
__int64 __fastcall CSpp::_BuildOneVolumeProp(
        CSpp *this,
        const unsigned __int16 *a2,
        struct _SPP_ONDISK_VOLUME_PROP *a3)
{
  __int64 v5; // rcx
  struct _SPP_ONDISK_VOLUME_PROP *v6; // rax
  __int16 v7; // ax
  __int64 v8; // rdx
  __int64 v9; // r8
  unsigned __int16 **v10; // rcx
  unsigned int i; // edi
  __int64 v12; // rbx
  unsigned int v13; // ebx
  int VolumeIdentifier; // [rsp+30h] [rbp-48h] BYREF
  __int16 v16; // [rsp+34h] [rbp-44h]
  __int16 v17; // [rsp+36h] [rbp-42h]
  CSpp *v18; // [rsp+A0h] [rbp+28h] BYREF
  unsigned int v19; // [rsp+A8h] [rbp+30h] BYREF
  unsigned __int16 **v20; // [rsp+B0h] [rbp+38h] BYREF
  LPVOID pv; // [rsp+B8h] [rbp+40h] BYREF

  v18 = this;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_Sq(*((_QWORD *)WPP_GLOBAL_Control + 2), (_DWORD)a2, (_DWORD)a3, (_DWORD)a2, (char)a3);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&VolumeIdentifier, "CSpp::_BuildOneVolumeProp", 3857, 1);
  v19 = 0;
  pv = 0;
  LODWORD(v18) = 0;
  v20 = 0;
  if ( a3 )
  {
    v5 = 48;
    v6 = a3;
    do
    {
      *(_BYTE *)v6 = 0;
      v6 = (struct _SPP_ONDISK_VOLUME_PROP *)((char *)v6 + 1);
      --v5;
    }
    while ( v5 );
  }
  v7 = 3867;
  if ( !a2 || (v16 = 3867, v7 = 3868, !a3) )
  {
    VolumeIdentifier = -2147024809;
LABEL_9:
    v17 = v7;
    goto LABEL_14;
  }
  VolumeIdentifier = 0;
  v16 = 3868;
  VolumeIdentifier = SxGetVolumeIdentifier(a2, (unsigned __int8 **)&pv, &v19);
  v7 = 3870;
  if ( VolumeIdentifier < 0 )
    goto LABEL_9;
  v16 = 3870;
  VolumeIdentifier = SxGetAllVolumeNames(a2, &v20, (unsigned int *)&v18);
  v7 = 3872;
  if ( VolumeIdentifier < 0 )
    goto LABEL_9;
  v16 = 3872;
  *((_DWORD *)a3 + 4) = v19;
  *((_QWORD *)a3 + 3) = pv;
  *((_DWORD *)a3 + 8) = (_DWORD)v18;
  *((_QWORD *)a3 + 5) = v20;
  pv = 0;
  v20 = 0;
LABEL_14:
  CoTaskMemFree(pv);
  v10 = v20;
  pv = 0;
  if ( v20 )
  {
    for ( i = 0; i < (unsigned int)v18; v10 = v20 )
    {
      v12 = i;
      CoTaskMemFree(v10[i++]);
      v20[v12] = 0;
    }
    CoTaskMemFree(v10);
    v20 = 0;
  }
  v13 = VolumeIdentifier;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&VolumeIdentifier, v8, v9);
  return v13;
}

```

## disassembly

```asm
0x180011fb0  mov     [rsp-20h+arg_0], rcx
0x180011fb5  push    rbp
0x180011fb6  push    rbx
0x180011fb7  push    rsi
0x180011fb8  push    rdi
0x180011fb9  mov     rbp, rsp
0x180011fbc  sub     rsp, 78h
0x180011fc0  mov     rbx, r8
0x180011fc3  mov     rdi, rdx
0x180011fc6  mov     rcx, cs:WPP_GLOBAL_Control
0x180011fcd  lea     rax, WPP_GLOBAL_Control
0x180011fd4  cmp     rcx, rax
0x180011fd7  jz      short loc_180011FF3
0x180011fd9  test    dword ptr [rcx+1Ch], 20000000h
0x180011fe0  jz      short loc_180011FF3
0x180011fe2  mov     rcx, [rcx+10h]
0x180011fe6  mov     r9, rdx
0x180011fe9  mov     [rsp+78h+var_58], rbx
0x180011fee  call    WPP_SF_Sq
0x180011ff3  mov     r9d, 1; unsigned __int16
0x180011ff9  lea     rdx, aCsppBuildonevo; "CSpp::_BuildOneVolumeProp"
0x180012000  mov     r8d, 0F11h; unsigned __int16
0x180012006  lea     rcx, [rbp+var_48]; this
0x18001200a  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18001200f  xor     esi, esi
0x180012011  mov     [rbp+arg_8], esi
0x180012014  mov     [rbp+pv], rsi
0x180012018  mov     dword ptr [rbp+arg_0], esi
0x18001201b  mov     [rbp+arg_10], rsi
0x18001201f  test    rbx, rbx
0x180012022  jz      short loc_180012036
0x180012024  lea     ecx, [rsi+30h]
0x180012027  mov     rax, rbx
0x18001202a  mov     [rax], sil
0x18001202d  inc     rax
0x180012030  sub     rcx, 1
0x180012034  jnz     short loc_18001202A
0x180012036  mov     eax, 0F1Bh
0x18001203b  test    rdi, rdi
0x18001203e  jnz     short loc_18001204D
0x180012040  mov     [rbp+var_48], 80070057h
0x180012047  mov     [rbp+var_42], ax
0x18001204b  jmp     short loc_1800120C6
0x18001204d  mov     [rbp+var_44], ax
0x180012051  mov     eax, 0F1Ch
0x180012056  test    rbx, rbx
0x180012059  jz      short loc_180012040
0x18001205b  lea     r8, [rbp+arg_8]; unsigned int *
0x18001205f  mov     [rbp+var_48], esi
0x180012062  lea     rdx, [rbp+pv]; unsigned __int8 **
0x180012066  mov     [rbp+var_44], ax
0x18001206a  mov     rcx, rdi; unsigned __int16 *
0x18001206d  call    ?SxGetVolumeIdentifier@@YAJPEBGPEAPEAEPEAK@Z; SxGetVolumeIdentifier(ushort const *,uchar * *,ulong *)
0x180012072  mov     [rbp+var_48], eax
0x180012075  test    eax, eax
0x180012077  mov     eax, 0F1Eh
0x18001207c  js      short loc_180012047
0x18001207e  lea     r8, [rbp+arg_0]; unsigned int *
0x180012082  mov     [rbp+var_44], ax
0x180012086  lea     rdx, [rbp+arg_10]; unsigned __int16 ***
0x18001208a  mov     rcx, rdi; unsigned __int16 *
0x18001208d  call    ?SxGetAllVolumeNames@@YAJPEBGPEAPEAPEAGPEAK@Z; SxGetAllVolumeNames(ushort const *,ushort * * *,ulong *)
0x180012092  mov     [rbp+var_48], eax
0x180012095  test    eax, eax
0x180012097  mov     eax, 0F20h
0x18001209c  js      short loc_180012047
0x18001209e  mov     [rbp+var_44], ax
0x1800120a2  mov     eax, [rbp+arg_8]
0x1800120a5  mov     [rbx+10h], eax
0x1800120a8  mov     rax, [rbp+pv]
0x1800120ac  mov     [rbx+18h], rax
0x1800120b0  mov     eax, dword ptr [rbp+arg_0]
0x1800120b3  mov     [rbx+20h], eax
0x1800120b6  mov     rax, [rbp+arg_10]
0x1800120ba  mov     [rbx+28h], rax
0x1800120be  mov     [rbp+pv], rsi
0x1800120c2  mov     [rbp+arg_10], rsi
0x1800120c6  mov     rcx, [rbp+pv]; pv
0x1800120ca  call    cs:__imp_CoTaskMemFree
0x1800120d0  mov     rcx, [rbp+arg_10]
0x1800120d4  mov     [rbp+pv], rsi
0x1800120d8  test    rcx, rcx
0x1800120db  jz      short loc_18001210D
0x1800120dd  mov     edi, esi
0x1800120df  cmp     dword ptr [rbp+arg_0], esi
0x1800120e2  jbe     short loc_180012103
0x1800120e4  mov     ebx, edi
0x1800120e6  mov     rcx, [rcx+rbx*8]; pv
0x1800120ea  call    cs:__imp_CoTaskMemFree
0x1800120f0  mov     rax, [rbp+arg_10]
0x1800120f4  inc     edi
0x1800120f6  mov     [rax+rbx*8], rsi
0x1800120fa  mov     rcx, [rbp+arg_10]; pv
0x1800120fe  cmp     edi, dword ptr [rbp+arg_0]
0x180012101  jb      short loc_1800120E4
0x180012103  call    cs:__imp_CoTaskMemFree
0x180012109  mov     [rbp+arg_10], rsi
0x18001210d  mov     ebx, [rbp+var_48]
0x180012110  lea     rcx, [rbp+var_48]; this
0x180012114  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180012119  mov     eax, ebx
0x18001211b  add     rsp, 78h
0x18001211f  pop     rdi
0x180012120  pop     rsi
0x180012121  pop     rbx
0x180012122  pop     rbp
0x180012123  retn
```
