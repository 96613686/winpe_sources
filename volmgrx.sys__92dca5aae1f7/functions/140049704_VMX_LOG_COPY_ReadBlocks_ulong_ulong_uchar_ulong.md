# VMX_LOG_COPY::ReadBlocks(ulong,ulong,uchar * *,ulong *)

- ea: `0x140049704`
- end: `0x140049afb`
- name: `?ReadBlocks@VMX_LOG_COPY@@QEAAJKKPEAPEAEPEAK@Z`
- size: `1015`
- prototype: `__int64 __fastcall(VMX_LOG_COPY *this, unsigned int, unsigned int, char **, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x14004931c`

## callees

- `0x1400099d8`
- `0x14001b78c`
- `0x14001bb80`
- `0x14001be80`
- `0x140034000`
- `0x140049704`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400497bf`
- `ntoskrnl!ExAllocatePool2` at `0x1400497bf`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400498f9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400499b5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140049a3c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400498f9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400499b5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140049a3c`

## pseudocode

```c
__int64 __fastcall VMX_LOG_COPY::ReadBlocks(
        VMX_LOG_COPY *this,
        unsigned int a2,
        unsigned int a3,
        char **a4,
        unsigned int *a5)
{
  __int64 v8; // rcx
  VMX_NOTIFICATION_QUEUE *v9; // rcx
  unsigned int v10; // edi
  __int64 v11; // rdx
  char *Pool2; // rsi
  VMX_NOTIFICATION_QUEUE *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // rax
  unsigned int v16; // edx
  char *v17; // r12
  unsigned int v18; // r13d
  unsigned int v19; // r8d
  unsigned int v20; // ecx
  unsigned int v21; // eax
  __int64 v22; // r10
  unsigned int v23; // r11d
  __int64 v24; // r9
  unsigned int v25; // r15d
  unsigned int v26; // eax
  int v27; // eax
  unsigned int v28; // eax
  unsigned int v30; // [rsp+20h] [rbp-88h]
  void *Src; // [rsp+28h] [rbp-80h] BYREF
  unsigned int v32; // [rsp+30h] [rbp-78h]
  unsigned int v33; // [rsp+34h] [rbp-74h]
  int v34; // [rsp+38h] [rbp-70h]
  size_t Size; // [rsp+40h] [rbp-68h]
  unsigned int v36; // [rsp+48h] [rbp-60h]
  __int64 v37; // [rsp+50h] [rbp-58h]
  __int64 v38; // [rsp+58h] [rbp-50h]
  __int64 v39; // [rsp+60h] [rbp-48h]
  unsigned int v40; // [rsp+B0h] [rbp+8h]

  Src = 0;
  *a5 = 0;
  v8 = *((_QWORD *)this + 3);
  if ( *(_DWORD *)(v8 + 40) )
  {
    if ( _InterlockedExchange((volatile __int32 *)(v8 + 44), 1) != 1 )
      VmxpSendRecordedFailureNotification(*((struct VMX_DISK_DEVICE **)this + 3));
    *((_BYTE *)this + 44) = 1;
    v9 = WPP_GLOBAL_Control;
    v10 = -1073741810;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x800) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      return v10;
    }
    v11 = 11;
    goto LABEL_52;
  }
  Pool2 = *a4;
  if ( *a4 )
    goto LABEL_15;
  if ( (unsigned __int64)a3 << 9 > 0xFFFFFFFF )
  {
    v9 = WPP_GLOBAL_Control;
    v10 = -1073741675;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x800) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      return v10;
    }
    v11 = 12;
LABEL_52:
    WPP_SF_d(*((_QWORD *)v9 + 3), v11, WPP_4b219bab5c283f1089a222952cd3541f_Traceguids, v10);
    return v10;
  }
  Pool2 = (char *)ExAllocatePool2(258, a3 << 9, 1967287638);
  if ( Pool2 )
  {
LABEL_15:
    v15 = *((_QWORD *)this + 3);
    v16 = 0;
    v34 = 0;
    v17 = Pool2;
    v18 = a3;
    v19 = *(_DWORD *)(v15 + 36);
    v20 = v19 >> 9;
    v21 = 0;
    v30 = v19 >> 9;
    v33 = v19;
    while ( v21 < *((_DWORD *)this + 10) )
    {
      v22 = *((_QWORD *)this + 4);
      v23 = v16;
      v24 = 16LL * v21;
      v36 = v16;
      v38 = v24;
      v39 = v22;
      v16 += *(_DWORD *)(v24 + v22 + 8) * v20;
      v32 = v16;
      if ( a2 >= v23 && a2 < v16 )
      {
        v37 = v19;
        v25 = v16 - a2;
        if ( v18 <= v16 - a2 )
          v25 = v18;
        Size = v25 << 9;
        if ( (int)VMX_DISK_DEVICE::Read(
                    *((VMX_DISK_DEVICE **)this + 3),
                    *(_QWORD *)(v24 + v22) * v37 + ((a2 - v23) << 9),
                    ((v20 + v25 - (v20 + v25 - 1) % v20) << 9) - 512,
                    (unsigned __int8 **)&Src) < 0 )
        {
          memset(v17, 0, Size);
          while ( v25 )
          {
            v26 = v30;
            if ( v25 < v30 )
              v26 = v25;
            v40 = v26;
            v27 = VMX_DISK_DEVICE::Read(
                    *((VMX_DISK_DEVICE **)this + 3),
                    *(_QWORD *)(v38 + v39) * v37 + ((a2 - v36) << 9),
                    v30 << 9,
                    (unsigned __int8 **)&Src);
            if ( v27 < 0 )
            {
              if ( v27 == -1073741670 )
              {
                if ( !*a4 )
                  ExFreePoolWithTag(Pool2, 0);
                v13 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
                  && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x800) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
                {
                  v14 = 14;
                  goto LABEL_45;
                }
                return 3221225626LL;
              }
              if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x800) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 3u )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 3),
                  15,
                  WPP_4b219bab5c283f1089a222952cd3541f_Traceguids,
                  (unsigned int)v27);
              }
              v28 = v40 << 9;
              *((_BYTE *)this + 44) = 1;
            }
            else
            {
              Size = v40 << 9;
              memmove(v17, Src, Size);
              ExFreePoolWithTag(Src, 0);
              v28 = Size;
            }
            v17 += v28;
            a2 += v40;
            v25 -= v40;
            v18 -= v40;
          }
        }
        else
        {
          memmove(v17, Src, Size);
          ExFreePoolWithTag(Src, 0);
          v18 -= v25;
          if ( !v18 )
            break;
          v17 += Size;
          a2 += v25;
        }
        v19 = v33;
        v16 = v32;
        v20 = v30;
      }
      v21 = ++v34;
    }
    *a4 = Pool2;
    *a5 = a3 - v18;
    return 0;
  }
  else
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
    {
      v14 = 13;
LABEL_45:
      WPP_SF_d(*((_QWORD *)v13 + 3), v14, WPP_4b219bab5c283f1089a222952cd3541f_Traceguids, 3221225626LL);
    }
    return 3221225626LL;
  }
}

```

## disassembly

```asm
0x140049704  mov     [rsp+arg_8], rbx
0x140049709  mov     [rsp+arg_18], r9
0x14004970e  push    rbp
0x14004970f  push    rsi
0x140049710  push    rdi
0x140049711  push    r12
0x140049713  push    r13
0x140049715  push    r14
0x140049717  push    r15
0x140049719  sub     rsp, 70h
0x14004971d  xor     ebx, ebx
0x14004971f  mov     ebp, r8d
0x140049722  mov     rdi, rcx
0x140049725  mov     [rsp+0A8h+Src], rbx
0x14004972a  mov     rcx, [rsp+0A8h+arg_20]
0x140049732  mov     r14d, edx
0x140049735  mov     [rcx], ebx
0x140049737  mov     rcx, [rdi+18h]
0x14004973b  cmp     [rcx+28h], ebx
0x14004973e  jz      short loc_140049795
0x140049740  lea     eax, [rbx+1]
0x140049743  xchg    eax, [rcx+2Ch]
0x140049746  cmp     eax, 1
0x140049749  jz      short loc_140049754
0x14004974b  mov     rcx, [rdi+18h]; struct VMX_DISK_DEVICE *
0x14004974f  call    ?VmxpSendRecordedFailureNotification@@YAXPEAVVMX_DISK_DEVICE@@@Z; VmxpSendRecordedFailureNotification(VMX_DISK_DEVICE *)
0x140049754  mov     byte ptr [rdi+2Ch], 1
0x140049758  mov     rcx, cs:WPP_GLOBAL_Control
0x14004975f  lea     rbx, WPP_GLOBAL_Control
0x140049766  mov     edi, 0C000000Eh
0x14004976b  cmp     rcx, rbx
0x14004976e  jz      loc_140049AE0
0x140049774  test    dword ptr [rcx+2Ch], 800h
0x14004977b  jz      loc_140049AE0
0x140049781  cmp     byte ptr [rcx+29h], 2
0x140049785  jb      loc_140049AE0
0x14004978b  mov     edx, 0Bh
0x140049790  jmp     loc_140049ACD
0x140049795  mov     rsi, [r9]
0x140049798  test    rsi, rsi
0x14004979b  jnz     short loc_140049809
0x14004979d  mov     rax, rbp
0x1400497a0  mov     ecx, 0FFFFFFFFh
0x1400497a5  shl     rax, 9
0x1400497a9  cmp     rax, rcx
0x1400497ac  ja      loc_140049AA1
0x1400497b2  mov     edx, eax
0x1400497b4  mov     ecx, 102h
0x1400497b9  mov     r8d, 75426D56h
0x1400497bf  call    cs:__imp_ExAllocatePool2
0x1400497c6  nop     dword ptr [rax+rax+00h]
0x1400497cb  mov     rsi, rax
0x1400497ce  test    rax, rax
0x1400497d1  jnz     short loc_140049809
0x1400497d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400497da  lea     rbx, WPP_GLOBAL_Control
0x1400497e1  cmp     rcx, rbx
0x1400497e4  jz      loc_140049A7E
0x1400497ea  test    dword ptr [rcx+2Ch], 800h
0x1400497f1  jz      loc_140049A7E
0x1400497f7  cmp     byte ptr [rcx+29h], 2
0x1400497fb  jb      loc_140049A7E
0x140049801  lea     edx, [rax+0Dh]
0x140049804  jmp     loc_140049A68
0x140049809  mov     rax, [rdi+18h]
0x14004980d  mov     edx, ebx
0x14004980f  mov     [rsp+0A8h+var_70], ebx
0x140049813  mov     r12, rsi
0x140049816  mov     r13d, ebp
0x140049819  mov     r8d, [rax+24h]
0x14004981d  mov     ecx, r8d
0x140049820  shr     ecx, 9
0x140049823  mov     eax, ebx
0x140049825  mov     [rsp+0A8h+var_88], ecx
0x140049829  lea     rbx, WPP_GLOBAL_Control
0x140049830  mov     [rsp+0A8h+var_74], r8d
0x140049835  cmp     eax, [rdi+28h]
0x140049838  jnb     loc_140049A85
0x14004983e  mov     r10, [rdi+20h]
0x140049842  mov     r11d, edx
0x140049845  mov     r9d, eax
0x140049848  mov     eax, ecx
0x14004984a  shl     r9, 4
0x14004984e  mov     [rsp+0A8h+var_60], edx
0x140049852  mov     [rsp+0A8h+var_50], r9
0x140049857  mov     [rsp+0A8h+var_48], r10
0x14004985c  imul    eax, [r9+r10+8]
0x140049862  add     edx, eax
0x140049864  mov     [rsp+0A8h+var_78], edx
0x140049868  cmp     r14d, r11d
0x14004986b  jb      loc_140049923
0x140049871  cmp     r14d, edx
0x140049874  jnb     loc_140049923
0x14004987a  mov     eax, r8d
0x14004987d  mov     r15d, edx
0x140049880  mov     [rsp+0A8h+var_58], rax
0x140049885  sub     r15d, r14d
0x140049888  cmp     r13d, r15d
0x14004988b  cmovbe  r15d, r13d
0x14004988f  xor     edx, edx
0x140049891  mov     eax, r15d
0x140049894  mov     r8d, r15d
0x140049897  shl     eax, 9
0x14004989a  mov     [rsp+0A8h+Size], rax
0x14004989f  lea     eax, [r15-1]
0x1400498a3  add     eax, ecx
0x1400498a5  div     ecx
0x1400498a7  mov     rax, [rsp+0A8h+var_58]
0x1400498ac  imul    rax, [r9+r10]
0x1400498b1  sub     r8d, edx
0x1400498b4  lea     r9, [rsp+0A8h+Src]; unsigned __int8 **
0x1400498b9  add     r8d, ecx
0x1400498bc  mov     edx, r14d
0x1400498bf  mov     rcx, [rdi+18h]; this
0x1400498c3  sub     edx, r11d
0x1400498c6  shl     edx, 9
0x1400498c9  shl     r8d, 9
0x1400498cd  add     rdx, rax; unsigned __int64
0x1400498d0  sub     r8d, 200h; unsigned int
0x1400498d7  call    ?Read@VMX_DISK_DEVICE@@QEAAJ_KKPEAPEAE@Z; VMX_DISK_DEVICE::Read(unsigned __int64,ulong,uchar * *)
0x1400498dc  mov     r8, [rsp+0A8h+Size]; Size
0x1400498e1  mov     rcx, r12; void *
0x1400498e4  test    eax, eax
0x1400498e6  js      short loc_140049932
0x1400498e8  mov     rdx, [rsp+0A8h+Src]; Src
0x1400498ed  call    memmove
0x1400498f2  mov     rcx, [rsp+0A8h+Src]; P
0x1400498f7  xor     edx, edx; Tag
0x1400498f9  call    cs:__imp_ExFreePoolWithTag
0x140049900  nop     dword ptr [rax+rax+00h]
0x140049905  sub     r13d, r15d
0x140049908  jz      loc_140049A85
0x14004990e  add     r12, [rsp+0A8h+Size]
0x140049913  add     r14d, r15d
0x140049916  mov     r8d, [rsp+0A8h+var_74]
0x14004991b  mov     edx, [rsp+0A8h+var_78]
0x14004991f  mov     ecx, [rsp+0A8h+var_88]
0x140049923  mov     eax, [rsp+0A8h+var_70]
0x140049927  inc     eax
0x140049929  mov     [rsp+0A8h+var_70], eax
0x14004992d  jmp     loc_140049835
0x140049932  xor     edx, edx; Val
0x140049934  call    memset
0x140049939  test    r15d, r15d
0x14004993c  jz      short loc_140049916
0x14004993e  mov     ecx, [rsp+0A8h+var_88]
0x140049942  mov     edx, r14d
0x140049945  mov     r9, [rsp+0A8h+var_48]
0x14004994a  mov     eax, ecx
0x14004994c  cmp     r15d, ecx
0x14004994f  mov     r8d, ecx
0x140049952  mov     rcx, [rsp+0A8h+var_50]
0x140049957  cmovb   eax, r15d
0x14004995b  sub     edx, [rsp+0A8h+var_60]
0x14004995f  mov     [rsp+0A8h+arg_0], eax
0x140049966  mov     rax, [rsp+0A8h+var_58]
0x14004996b  imul    rax, [rcx+r9]
0x140049970  mov     rcx, [rdi+18h]; this
0x140049974  lea     r9, [rsp+0A8h+Src]; unsigned __int8 **
0x140049979  shl     edx, 9
0x14004997c  add     rdx, rax; unsigned __int64
0x14004997f  shl     r8d, 9; unsigned int
0x140049983  call    ?Read@VMX_DISK_DEVICE@@QEAAJ_KKPEAPEAE@Z; VMX_DISK_DEVICE::Read(unsigned __int64,ulong,uchar * *)
0x140049988  mov     r9d, eax
0x14004998b  test    eax, eax
0x14004998d  js      short loc_1400499C8
0x14004998f  mov     eax, [rsp+0A8h+arg_0]
0x140049996  mov     rcx, r12; void *
0x140049999  mov     rdx, [rsp+0A8h+Src]; Src
0x14004999e  shl     eax, 9
0x1400499a1  mov     r8d, eax; Size
0x1400499a4  mov     [rsp+0A8h+Size], rax
0x1400499a9  call    memmove
0x1400499ae  mov     rcx, [rsp+0A8h+Src]; P
0x1400499b3  xor     edx, edx; Tag
0x1400499b5  call    cs:__imp_ExFreePoolWithTag
0x1400499bc  nop     dword ptr [rax+rax+00h]
0x1400499c1  mov     rax, [rsp+0A8h+Size]
0x1400499c6  jmp     short loc_140049A0F
0x1400499c8  cmp     r9d, 0C000009Ah
0x1400499cf  jz      short loc_140049A29
0x1400499d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400499d8  cmp     rcx, rbx
0x1400499db  jz      short loc_140049A01
0x1400499dd  test    dword ptr [rcx+2Ch], 800h
0x1400499e4  jz      short loc_140049A01
0x1400499e6  cmp     byte ptr [rcx+29h], 3
0x1400499ea  jb      short loc_140049A01
0x1400499ec  mov     rcx, [rcx+18h]
0x1400499f0  lea     r8, WPP_4b219bab5c283f1089a222952cd3541f_Traceguids
0x1400499f7  mov     edx, 0Fh
0x1400499fc  call    WPP_SF_d
0x140049a01  mov     eax, [rsp+0A8h+arg_0]
0x140049a08  shl     eax, 9
0x140049a0b  mov     byte ptr [rdi+2Ch], 1
0x140049a0f  mov     eax, eax
0x140049a11  add     r12, rax
0x140049a14  mov     eax, [rsp+0A8h+arg_0]
0x140049a1b  add     r14d, eax
0x140049a1e  sub     r15d, eax
0x140049a21  sub     r13d, eax
0x140049a24  jmp     loc_140049939
0x140049a29  mov     rax, [rsp+0A8h+arg_18]
0x140049a31  cmp     qword ptr [rax], 0
0x140049a35  jnz     short loc_140049A48
0x140049a37  xor     edx, edx; Tag
0x140049a39  mov     rcx, rsi; P
0x140049a3c  call    cs:__imp_ExFreePoolWithTag
0x140049a43  nop     dword ptr [rax+rax+00h]
0x140049a48  mov     rcx, cs:WPP_GLOBAL_Control
0x140049a4f  cmp     rcx, rbx
0x140049a52  jz      short loc_140049A7E
0x140049a54  test    dword ptr [rcx+2Ch], 800h
0x140049a5b  jz      short loc_140049A7E
0x140049a5d  cmp     byte ptr [rcx+29h], 2
0x140049a61  jb      short loc_140049A7E
0x140049a63  mov     edx, 0Eh
0x140049a68  mov     rcx, [rcx+18h]
0x140049a6c  lea     r8, WPP_4b219bab5c283f1089a222952cd3541f_Traceguids
0x140049a73  mov     r9d, 0C000009Ah
0x140049a79  call    WPP_SF_d
0x140049a7e  mov     eax, 0C000009Ah
0x140049a83  jmp     short loc_140049AE2
0x140049a85  mov     rax, [rsp+0A8h+arg_18]
0x140049a8d  sub     ebp, r13d
0x140049a90  mov     [rax], rsi
0x140049a93  mov     rax, [rsp+0A8h+arg_20]
0x140049a9b  mov     [rax], ebp
0x140049a9d  xor     eax, eax
0x140049a9f  jmp     short loc_140049AE2
0x140049aa1  mov     rcx, cs:WPP_GLOBAL_Control
0x140049aa8  lea     rbx, WPP_GLOBAL_Control
0x140049aaf  mov     edi, 0C0000095h
0x140049ab4  cmp     rcx, rbx
0x140049ab7  jz      short loc_140049AE0
0x140049ab9  test    dword ptr [rcx+2Ch], 800h
0x140049ac0  jz      short loc_140049AE0
0x140049ac2  cmp     byte ptr [rcx+29h], 2
0x140049ac6  jb      short loc_140049AE0
0x140049ac8  mov     edx, 0Ch
0x140049acd  mov     rcx, [rcx+18h]
0x140049ad1  lea     r8, WPP_4b219bab5c283f1089a222952cd3541f_Traceguids
0x140049ad8  mov     r9d, edi
0x140049adb  call    WPP_SF_d
0x140049ae0  mov     eax, edi
0x140049ae2  mov     rbx, [rsp+0A8h+arg_8]
0x140049aea  add     rsp, 70h
0x140049aee  pop     r15
0x140049af0  pop     r14
0x140049af2  pop     r13
0x140049af4  pop     r12
0x140049af6  pop     rdi
0x140049af7  pop     rsi
0x140049af8  pop     rbp
0x140049af9  retn
```
