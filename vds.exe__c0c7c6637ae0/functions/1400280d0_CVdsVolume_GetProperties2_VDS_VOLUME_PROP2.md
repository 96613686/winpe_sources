# CVdsVolume::GetProperties2(_VDS_VOLUME_PROP2 *)

- ea: `0x1400280d0`
- end: `0x140028338`
- name: `?GetProperties2@CVdsVolume@@UEAAJPEAU_VDS_VOLUME_PROP2@@@Z`
- size: `616`
- prototype: `int(CVdsVolume *__hidden this, struct _VDS_VOLUME_PROP2 *)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x140003710`
- `0x140004360`
- `0x140006e60`
- `0x1400280d0`
- `0x14002e123`
- `0x140052e80`
- `0x140056010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1400281f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1400281f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400282db`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400282db`
- `vdsutil!GetVolumeUniqueId` at `0x14002828f`
- `vdsutil!GetVolumeUniqueId` at `0x14002828f`
- `vdsutil!VdsTraceEx` at `0x140028198`
- `vdsutil!VdsTraceEx` at `0x1400281cb`
- `vdsutil!VdsTraceEx` at `0x140028246`
- `vdsutil!VdsTraceEx` at `0x1400282ad`
- `vdsutil!VdsTraceEx` at `0x140028198`
- `vdsutil!VdsTraceEx` at `0x1400281cb`
- `vdsutil!VdsTraceEx` at `0x140028246`
- `vdsutil!VdsTraceEx` at `0x1400282ad`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140028127`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140028127`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140028308`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140028308`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CVdsVolume::GetProperties2(CVdsVolume *this, struct _VDS_VOLUME_PROP2 *a2)
{
  signed int v4; // ebx
  int v5; // edi
  int v6; // eax
  __int64 v7; // rax
  SIZE_T v8; // rbx
  WCHAR *v9; // rax
  signed int VolumeUniqueId; // esi
  __int64 v12; // [rsp+20h] [rbp-60h] BYREF
  int v13; // [rsp+28h] [rbp-58h]
  _BYTE v14[16]; // [rsp+30h] [rbp-50h] BYREF
  VDS_OBJECT_ID v15; // [rsp+40h] [rbp-40h] BYREF
  __int128 v16; // [rsp+50h] [rbp-30h]
  __int128 v17; // [rsp+60h] [rbp-20h]
  LPVOID pv; // [rsp+70h] [rbp-10h]

  v15 = 0;
  v16 = 0;
  v17 = 0;
  pv = 0;
  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v14, 0x5Eu, "CVdsVolume::GetProperties2()");
  v15 = 0;
  v16 = 0;
  v17 = 0;
  pv = 0;
  v12 = 0;
  v13 = 0;
  v4 = CVdsOperationEntry::BeginOperation((CVdsOperationEntry *)&v12);
  if ( v4 < 0 )
    goto LABEL_28;
  v5 = 0;
  memset_0(a2, 0, sizeof(struct _VDS_VOLUME_PROP2));
  if ( !*((_QWORD *)this + 15) )
  {
    v4 = -2147212216;
    VdsTraceEx(94, 1, "CVdsVolume::GetProperties2, 1, hr= %lX", 2147755080LL);
    goto LABEL_20;
  }
  v6 = (*(__int64 (__fastcall **)(char *, VDS_OBJECT_ID *))(*((_QWORD *)this - 1) + 24LL))((char *)this - 8, &v15);
  v4 = v6;
  if ( v6 < 0 )
  {
    VdsTraceEx(94, 1, "CVdsVolume::GetProperties2, 2, hr= %lX", v6);
    v5 = v4;
  }
  if ( pv )
  {
    v7 = -1;
    do
      ++v7;
    while ( *((_WORD *)pv + v7) );
    v8 = 2 * v7 + 2;
    v9 = (WCHAR *)CoTaskMemAlloc(v8);
    a2->pwszName = v9;
    if ( !v9 )
    {
      v4 = -2147024882;
      VdsTraceEx(94, 1, "CVdsVolume::GetProperties2, 3, hr= %lX", 2147942414LL);
      goto LABEL_20;
    }
    v4 = StringCchCopyW(v9, v8, (const unsigned __int16 *)pv);
    if ( v4 < 0 )
    {
      v4 = -2147212216;
      VdsTraceEx(94, 1, "CVdsVolume::GetProperties2, 4, hr= %lX", -2147212216);
      if ( v5 >= 0 )
        v5 = -2147212216;
    }
  }
  a2->id = v15;
  *(_OWORD *)&a2->type = v16;
  *(_OWORD *)&a2->ullSize = v17;
  VolumeUniqueId = GetVolumeUniqueId(a2);
  if ( VolumeUniqueId )
  {
    VdsTraceEx(94, 1, "CVdsVolume::GetProperties2, 5, hr= %lX", v4);
    v4 = VolumeUniqueId > 0 ? (unsigned __int16)VolumeUniqueId | 0x80070000 : VolumeUniqueId;
    if ( v5 >= 0 )
      v5 = v4;
  }
LABEL_20:
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  if ( v5 >= 0 )
  {
    if ( !v5 )
      goto LABEL_26;
    if ( v4 < 0 )
    {
LABEL_27:
      v4 = 272149;
      goto LABEL_28;
    }
  }
  v4 = v5;
LABEL_26:
  if ( v4 < 0 )
    goto LABEL_27;
LABEL_28:
  CVdsOperationEntry::~CVdsOperationEntry((CVdsOperationEntry *)&v12);
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v14);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1400280d0  mov     [rsp-28h+arg_10], rbx
0x1400280d5  mov     [rsp-28h+arg_18], rsi
0x1400280da  push    rbp
0x1400280db  push    rdi
0x1400280dc  push    r12
0x1400280de  push    r13
0x1400280e0  push    r15
0x1400280e2  mov     rbp, rsp
0x1400280e5  sub     rsp, 80h
0x1400280ec  mov     rax, cs:__security_cookie
0x1400280f3  xor     rax, rsp
0x1400280f6  mov     [rbp+var_8], rax
0x1400280fa  mov     r15, rdx
0x1400280fd  mov     rsi, rcx
0x140028100  xorps   xmm0, xmm0
0x140028103  xor     eax, eax
0x140028105  movups  [rbp+var_40], xmm0
0x140028109  movups  [rbp+var_30], xmm0
0x14002810d  movups  [rbp+var_20], xmm0
0x140028111  mov     [rbp+pv], rax
0x140028115  lea     r8, aCvdsvolumeGetp_8; "CVdsVolume::GetProperties2()"
0x14002811c  lea     r13d, [rax+5Eh]
0x140028120  mov     edx, r13d
0x140028123  lea     rcx, [rbp+var_50]
0x140028127  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x14002812d  nop
0x14002812e  xorps   xmm0, xmm0
0x140028131  xor     eax, eax
0x140028133  movups  [rbp+var_40], xmm0
0x140028137  movups  [rbp+var_30], xmm0
0x14002813b  movups  [rbp+var_20], xmm0
0x14002813f  mov     [rbp+pv], rax
0x140028143  xor     r12d, r12d
0x140028146  mov     [rbp+var_60], r12
0x14002814a  mov     [rbp+var_58], r12d
0x14002814e  lea     rcx, [rbp+var_60]; this
0x140028152  call    ?BeginOperation@CVdsOperationEntry@@QEAAJXZ; CVdsOperationEntry::BeginOperation(void)
0x140028157  mov     ebx, eax
0x140028159  test    eax, eax
0x14002815b  js      loc_1400282FA
0x140028161  mov     edi, r12d
0x140028164  xor     edx, edx; Val
0x140028166  lea     r8d, [r13-16h]; Size
0x14002816a  mov     rcx, r15; void *
0x14002816d  call    memset_0
0x140028172  lea     rcx, [rsi-8]
0x140028176  cmp     [rcx+80h], r12
0x14002817d  jnz     short loc_1400281A3
0x14002817f  mov     esi, 80042448h
0x140028184  mov     ebx, esi
0x140028186  mov     r9d, esi
0x140028189  lea     r8, aCvdsvolumeGetp_0; "CVdsVolume::GetProperties2, 1, hr= %lX"
0x140028190  mov     edx, 1
0x140028195  mov     ecx, r13d
0x140028198  call    cs:__imp_VdsTraceEx
0x14002819e  jmp     loc_1400282D2
0x1400281a3  mov     rax, [rcx]
0x1400281a6  lea     rdx, [rbp+var_40]
0x1400281aa  mov     rax, [rax+18h]
0x1400281ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400281b3  mov     ebx, eax
0x1400281b5  test    eax, eax
0x1400281b7  jns     short loc_1400281D3
0x1400281b9  mov     r9d, eax
0x1400281bc  lea     r8, aCvdsvolumeGetp_10; "CVdsVolume::GetProperties2, 2, hr= %lX"
0x1400281c3  mov     edx, 1
0x1400281c8  mov     ecx, r13d
0x1400281cb  call    cs:__imp_VdsTraceEx
0x1400281d1  mov     edi, ebx
0x1400281d3  mov     rcx, [rbp+pv]
0x1400281d7  test    rcx, rcx
0x1400281da  jz      short loc_140028251
0x1400281dc  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400281e0  inc     rax
0x1400281e3  cmp     [rcx+rax*2], r12w
0x1400281e8  jnz     short loc_1400281E0
0x1400281ea  lea     rbx, ds:2[rax*2]
0x1400281f2  mov     rcx, rbx; cb
0x1400281f5  call    cs:__imp_CoTaskMemAlloc
0x1400281fb  mov     [r15+38h], rax
0x1400281ff  test    rax, rax
0x140028202  jnz     short loc_140028218
0x140028204  mov     ebx, 8007000Eh
0x140028209  mov     r9d, ebx
0x14002820c  lea     r8, aCvdsvolumeGetp_11; "CVdsVolume::GetProperties2, 3, hr= %lX"
0x140028213  jmp     loc_140028190
0x140028218  mov     r8, [rbp+pv]; unsigned __int16 *
0x14002821c  mov     rdx, rbx; unsigned __int64
0x14002821f  mov     rcx, rax; unsigned __int16 *
0x140028222  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140028227  mov     ebx, eax
0x140028229  test    eax, eax
0x14002822b  jns     short loc_140028251
0x14002822d  mov     esi, 80042448h
0x140028232  mov     ebx, esi
0x140028234  mov     r9d, esi
0x140028237  lea     r8, aCvdsvolumeGetp_1; "CVdsVolume::GetProperties2, 4, hr= %lX"
0x14002823e  mov     edx, 1
0x140028243  mov     ecx, r13d
0x140028246  call    cs:__imp_VdsTraceEx
0x14002824c  test    edi, edi
0x14002824e  cmovns  edi, esi
0x140028251  movups  xmm0, [rbp+var_40]
0x140028255  movdqu  xmmword ptr [r15], xmm0
0x14002825a  mov     eax, dword ptr [rbp+var_30]
0x14002825d  mov     [r15+10h], eax
0x140028261  mov     eax, dword ptr [rbp+var_30+4]
0x140028264  mov     [r15+14h], eax
0x140028268  mov     eax, dword ptr [rbp+var_30+8]
0x14002826b  mov     [r15+18h], eax
0x14002826f  mov     eax, dword ptr [rbp+var_30+0Ch]
0x140028272  mov     [r15+1Ch], eax
0x140028276  mov     rax, qword ptr [rbp+var_20]
0x14002827a  mov     [r15+20h], rax
0x14002827e  mov     eax, dword ptr [rbp+var_20+8]
0x140028281  mov     [r15+28h], eax
0x140028285  mov     eax, dword ptr [rbp+var_20+0Ch]
0x140028288  mov     [r15+2Ch], eax
0x14002828c  mov     rcx, r15
0x14002828f  call    cs:__imp_GetVolumeUniqueId
0x140028295  mov     esi, eax
0x140028297  test    eax, eax
0x140028299  jz      short loc_1400282D2
0x14002829b  mov     r9d, ebx
0x14002829e  lea     r8, aCvdsvolumeGetp_12; "CVdsVolume::GetProperties2, 5, hr= %lX"
0x1400282a5  mov     edx, 1
0x1400282aa  mov     ecx, r13d
0x1400282ad  call    cs:__imp_VdsTraceEx
0x1400282b3  test    esi, esi
0x1400282b5  jg      short loc_1400282BB
0x1400282b7  mov     ebx, esi
0x1400282b9  jmp     short loc_1400282C4
0x1400282bb  movzx   ebx, si
0x1400282be  or      ebx, 80070000h
0x1400282c4  test    edi, edi
0x1400282c6  js      short loc_1400282CE
0x1400282c8  test    ebx, ebx
0x1400282ca  js      short loc_1400282D0
0x1400282cc  test    edi, edi
0x1400282ce  jnz     short loc_1400282D2
0x1400282d0  mov     edi, ebx
0x1400282d2  mov     rcx, [rbp+pv]; pv
0x1400282d6  test    rcx, rcx
0x1400282d9  jz      short loc_1400282E5
0x1400282db  call    cs:__imp_CoTaskMemFree
0x1400282e1  mov     [rbp+pv], r12
0x1400282e5  test    edi, edi
0x1400282e7  js      short loc_1400282EF
0x1400282e9  jz      short loc_1400282F1
0x1400282eb  test    ebx, ebx
0x1400282ed  js      short loc_1400282F5
0x1400282ef  mov     ebx, edi
0x1400282f1  test    ebx, ebx
0x1400282f3  jns     short loc_1400282FA
0x1400282f5  mov     ebx, 42715h
0x1400282fa  lea     rcx, [rbp+var_60]; this
0x1400282fe  call    ??1CVdsOperationEntry@@QEAA@XZ; CVdsOperationEntry::~CVdsOperationEntry(void)
0x140028303  nop
0x140028304  lea     rcx, [rbp+var_50]
0x140028308  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x14002830e  mov     eax, ebx
0x140028310  mov     rcx, [rbp+var_8]
0x140028314  xor     rcx, rsp; StackCookie
0x140028317  call    __security_check_cookie
0x14002831c  lea     r11, [rsp+80h+var_s0]
0x140028324  mov     rbx, [r11+40h]
0x140028328  mov     rsi, [r11+48h]
0x14002832c  mov     rsp, r11
0x14002832f  pop     r15
0x140028331  pop     r13
0x140028333  pop     r12
0x140028335  pop     rdi
0x140028336  pop     rbp
0x140028337  retn
```
