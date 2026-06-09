# MtMgrGetSymbolicNames(ushort const *,ushort * *)

- ea: `0x1400212d4`
- end: `0x140021550`
- name: `?MtMgrGetSymbolicNames@@YAHPEBGPEAPEAG@Z`
- size: `636`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `6`
- tags: `reparse_path, service_task, broker_com_uri`

## callers

- `0x1400205d0`
- `0x1400d4088`

## callees

- `0x1400212d4`
- `0x140021cd8`
- `0x140025abc`
- `0x14003b0c0`
- `0x1400d257c`
- `0x1400da314`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140021537`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140021537`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140021368`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140021382`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140021368`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140021382`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400214f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140021501`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400214f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140021501`

## string_xrefs

- `0x140021492`: `pmwszSymbolicNames`
- `0x140021308`: `MtMgrGetSymbolicNames`
- `0x14002151d`: `MtMgrGetSymbolicNames`
- `0x1400214b6`: `ppmwszOutSymbolicNames`

## pseudocode

```c
__int64 __fastcall MtMgrGetSymbolicNames(const unsigned __int16 *a1, unsigned __int16 **a2)
{
  struct _DRIVE_LAYOUT_INFORMATION_EX *v4; // rcx
  unsigned int v5; // r15d
  _DWORD *v6; // rdi
  unsigned int v7; // ebp
  DWORD LastError; // esi
  DWORD v9; // eax
  int v10; // r8d
  unsigned int i; // edx
  __int64 v12; // rax
  unsigned __int16 *v13; // r14
  unsigned __int16 *v14; // r12
  unsigned int v15; // ecx
  __int64 v16; // rbx
  LPVOID pv; // [rsp+80h] [rbp+8h] BYREF

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x100000000LL) != 0 )
  {
    WPP_SF_S(
      *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
      10,
      WPP_1ff3ecedd42930a16d896984b72cfff5_Traceguids,
      L"MtMgrGetSymbolicNames");
    v4 = WPP_GLOBAL_Control;
  }
  v5 = 0;
  pv = 0;
  v6 = 0;
  if ( a1 && *a1 )
  {
    if ( a2 )
    {
      if ( (unsigned int)MtMgrGetMountPoints(a1, (int)a2, (struct _MOUNTMGR_MOUNT_POINTS **)&pv) )
      {
        v6 = pv;
        v10 = 2;
        for ( i = 0; i < *((_DWORD *)pv + 1); v10 += *((unsigned __int16 *)pv + 12 * v12 + 6) + 2 )
          v12 = i++;
        v13 = (unsigned __int16 *)ASR_ALLOC((unsigned int)(v10 + 2));
        if ( v13 )
        {
          LastError = 0;
          v7 = 1;
          if ( v6[1] )
          {
            v14 = v13;
            do
            {
              v15 = LOWORD(v6[6 * v5 + 3]);
              if ( (_WORD)v15 )
              {
                v16 = v15 >> 1;
                memcpy_0(v14, (char *)v6 + (unsigned int)v6[6 * v5 + 2], LOWORD(v6[6 * v5 + 3]));
                v14[v16] = 0;
                v14 += (unsigned int)(v16 + 1);
              }
              ++v5;
            }
            while ( v5 < v6[1] );
            *v14 = 0;
          }
          else
          {
            *(_DWORD *)v13 = 0;
          }
          *a2 = v13;
        }
        else
        {
          v7 = 0;
          LastError = 14;
          if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
            && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
          {
            WPP_SF_Ds(
              *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
              32,
              (unsigned int)WPP_78d403bd48723deb5f738664aa5853e8_Traceguids,
              14,
              "pmwszSymbolicNames");
          }
        }
      }
      else
      {
        v7 = 0;
        LastError = GetLastError();
        if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
          && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
        {
          v9 = GetLastError();
          WPP_SF_Ds(
            *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
            31,
            (unsigned int)WPP_78d403bd48723deb5f738664aa5853e8_Traceguids,
            v9,
            "GetLastError()");
        }
        v6 = pv;
      }
    }
    else
    {
      v7 = 0;
      LastError = 87;
      if ( v4 != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
        && (v4->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
      {
        WPP_SF_Ds(
          *(_QWORD *)v4->Gpt.DiskId.Data4,
          30,
          (unsigned int)WPP_78d403bd48723deb5f738664aa5853e8_Traceguids,
          87,
          "ppmwszOutSymbolicNames");
      }
    }
  }
  else
  {
    v7 = 0;
    LastError = 87;
    if ( v4 != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
      && (v4->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
    {
      WPP_SF_Ds(
        *(_QWORD *)v4->Gpt.DiskId.Data4,
        29,
        (unsigned int)WPP_78d403bd48723deb5f738664aa5853e8_Traceguids,
        87,
        "pwszDeviceName");
    }
  }
  CoTaskMemFree(0);
  CoTaskMemFree(v6);
  if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x100000000LL) != 0 )
  {
    WPP_SF_S(
      *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
      11,
      WPP_1ff3ecedd42930a16d896984b72cfff5_Traceguids,
      L"MtMgrGetSymbolicNames");
  }
  SetLastError(LastError);
  return v7;
}

```

## disassembly

```asm
0x1400212d4  push    rbx
0x1400212d6  push    rbp
0x1400212d7  push    rsi
0x1400212d8  push    rdi
0x1400212d9  push    r12
0x1400212db  push    r13
0x1400212dd  push    r14
0x1400212df  push    r15
0x1400212e1  sub     rsp, 38h
0x1400212e5  mov     r13, rdx
0x1400212e8  mov     rbx, rcx
0x1400212eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400212f2  lea     r12, WPP_GLOBAL_Control
0x1400212f9  cmp     rcx, r12
0x1400212fc  jz      short loc_140021327
0x1400212fe  test    byte ptr [rcx+1Ch], 1
0x140021302  jz      short loc_140021327
0x140021304  mov     rcx, [rcx+10h]
0x140021308  lea     r9, aMtmgrgetsymbol; "MtMgrGetSymbolicNames"
0x14002130f  mov     edx, 0Ah
0x140021314  lea     r8, WPP_1ff3ecedd42930a16d896984b72cfff5_Traceguids
0x14002131b  call    WPP_SF_S
0x140021320  mov     rcx, cs:WPP_GLOBAL_Control
0x140021327  xor     r15d, r15d
0x14002132a  mov     [rsp+78h+pv], r15
0x140021332  mov     edi, r15d
0x140021335  test    rbx, rbx
0x140021338  jz      loc_1400214BF
0x14002133e  cmp     [rbx], r15w
0x140021342  jz      loc_1400214BF
0x140021348  test    r13, r13
0x14002134b  jz      loc_14002149B
0x140021351  lea     r8, [rsp+78h+pv]; struct _MOUNTMGR_MOUNT_POINTS **
0x140021359  mov     rcx, rbx; unsigned __int16 *
0x14002135c  call    ?MtMgrGetMountPoints@@YAHPEBGHPEAPEAU_MOUNTMGR_MOUNT_POINTS@@@Z; MtMgrGetMountPoints(ushort const *,int,_MOUNTMGR_MOUNT_POINTS * *)
0x140021361  test    eax, eax
0x140021363  jnz     short loc_1400213BF
0x140021365  mov     ebp, r15d
0x140021368  call    cs:__imp_GetLastError
0x14002136e  mov     esi, eax
0x140021370  mov     rax, cs:WPP_GLOBAL_Control
0x140021377  cmp     rax, r12
0x14002137a  jz      short loc_1400213B2
0x14002137c  test    byte ptr [rax+1Ch], 8
0x140021380  jz      short loc_1400213B2
0x140021382  call    cs:__imp_GetLastError
0x140021388  lea     rcx, aGetlasterror_1; "GetLastError()"
0x14002138f  mov     r9d, eax
0x140021392  mov     [rsp+78h+var_58], rcx
0x140021397  lea     edx, [r15+1Fh]
0x14002139b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400213a2  lea     r8, WPP_78d403bd48723deb5f738664aa5853e8_Traceguids
0x1400213a9  mov     rcx, [rcx+10h]
0x1400213ad  call    WPP_SF_Ds
0x1400213b2  mov     rdi, [rsp+78h+pv]
0x1400213ba  jmp     loc_1400214F6
0x1400213bf  mov     rdi, [rsp+78h+pv]
0x1400213c7  mov     r8d, 2
0x1400213cd  mov     edx, r15d
0x1400213d0  cmp     [rdi+4], r15d
0x1400213d4  jbe     short loc_1400213EF
0x1400213d6  mov     eax, edx
0x1400213d8  add     r8d, 2
0x1400213dc  inc     edx
0x1400213de  lea     rcx, [rax+rax*2]
0x1400213e2  movzx   eax, word ptr [rdi+rcx*8+0Ch]
0x1400213e7  add     r8d, eax
0x1400213ea  cmp     edx, [rdi+4]
0x1400213ed  jb      short loc_1400213D6
0x1400213ef  lea     ecx, [r8+2]; Size
0x1400213f3  call    ?ASR_ALLOC@@YAPEAXK@Z; ASR_ALLOC(ulong)
0x1400213f8  mov     r14, rax
0x1400213fb  test    rax, rax
0x1400213fe  jz      short loc_140021472
0x140021400  mov     eax, [rdi+4]
0x140021403  mov     esi, r15d
0x140021406  mov     ebp, 1
0x14002140b  test    eax, eax
0x14002140d  jnz     short loc_140021414
0x14002140f  mov     [r14], r15d
0x140021412  jmp     short loc_140021469
0x140021414  xor     r8d, r8d
0x140021417  mov     r12, r14
0x14002141a  test    eax, eax
0x14002141c  jz      short loc_14002145D
0x14002141e  mov     eax, r15d
0x140021421  lea     rdx, [rax+rax*2]
0x140021425  movzx   ecx, word ptr [rdi+rdx*8+0Ch]
0x14002142a  test    cx, cx
0x14002142d  jz      short loc_140021454
0x14002142f  mov     edx, [rdi+rdx*8+8]
0x140021433  mov     ebx, ecx
0x140021435  mov     r8d, ecx; Size
0x140021438  shr     ebx, 1
0x14002143a  add     rdx, rdi; Src
0x14002143d  mov     rcx, r12; void *
0x140021440  call    memcpy_0
0x140021445  xor     r8d, r8d
0x140021448  lea     eax, [rbx+1]
0x14002144b  mov     [r12+rbx*2], r8w
0x140021450  lea     r12, [r12+rax*2]
0x140021454  inc     r15d
0x140021457  cmp     r15d, [rdi+4]
0x14002145b  jb      short loc_14002141E
0x14002145d  mov     [r12], r8w
0x140021462  lea     r12, WPP_GLOBAL_Control
0x140021469  mov     [r13+0], r14
0x14002146d  jmp     loc_1400214F6
0x140021472  mov     ebp, r15d
0x140021475  mov     esi, 0Eh
0x14002147a  mov     rcx, cs:WPP_GLOBAL_Control
0x140021481  cmp     rcx, r12
0x140021484  jz      short loc_1400214F6
0x140021486  test    byte ptr [rcx+1Ch], 8
0x14002148a  jz      short loc_1400214F6
0x14002148c  lea     edx, [rsi+12h]
0x14002148f  mov     r9d, esi
0x140021492  lea     rax, aPmwszsymbolicn; "pmwszSymbolicNames"
0x140021499  jmp     short loc_1400214E1
0x14002149b  mov     r9d, 57h ; 'W'
0x1400214a1  mov     ebp, r15d
0x1400214a4  mov     esi, r9d
0x1400214a7  cmp     rcx, r12
0x1400214aa  jz      short loc_1400214F6
0x1400214ac  test    byte ptr [rcx+1Ch], 8
0x1400214b0  jz      short loc_1400214F6
0x1400214b2  lea     edx, [r9-39h]
0x1400214b6  lea     rax, aPpmwszoutsymbo; "ppmwszOutSymbolicNames"
0x1400214bd  jmp     short loc_1400214E1
0x1400214bf  mov     r9d, 57h ; 'W'
0x1400214c5  mov     ebp, r15d
0x1400214c8  mov     esi, r9d
0x1400214cb  cmp     rcx, r12
0x1400214ce  jz      short loc_1400214F6
0x1400214d0  test    byte ptr [rcx+1Ch], 8
0x1400214d4  jz      short loc_1400214F6
0x1400214d6  lea     edx, [r9-3Ah]
0x1400214da  lea     rax, aPwszdevicename; "pwszDeviceName"
0x1400214e1  mov     rcx, [rcx+10h]
0x1400214e5  lea     r8, WPP_78d403bd48723deb5f738664aa5853e8_Traceguids
0x1400214ec  mov     [rsp+78h+var_58], rax
0x1400214f1  call    WPP_SF_Ds
0x1400214f6  xor     ecx, ecx; pv
0x1400214f8  call    cs:__imp_CoTaskMemFree
0x1400214fe  mov     rcx, rdi; pv
0x140021501  call    cs:__imp_CoTaskMemFree
0x140021507  mov     rcx, cs:WPP_GLOBAL_Control
0x14002150e  cmp     rcx, r12
0x140021511  jz      short loc_140021535
0x140021513  test    byte ptr [rcx+1Ch], 1
0x140021517  jz      short loc_140021535
0x140021519  mov     rcx, [rcx+10h]
0x14002151d  lea     r9, aMtmgrgetsymbol; "MtMgrGetSymbolicNames"
0x140021524  mov     edx, 0Bh
0x140021529  lea     r8, WPP_1ff3ecedd42930a16d896984b72cfff5_Traceguids
0x140021530  call    WPP_SF_S
0x140021535  mov     ecx, esi; dwErrCode
0x140021537  call    cs:__imp_SetLastError
0x14002153d  mov     eax, ebp
0x14002153f  add     rsp, 38h
0x140021543  pop     r15
0x140021545  pop     r14
0x140021547  pop     r13
0x140021549  pop     r12
0x14002154b  pop     rdi
0x14002154c  pop     rsi
0x14002154d  pop     rbp
0x14002154e  pop     rbx
0x14002154f  retn
```
