# COMXProc::_AdviseVolumeChangeHelper(Storage::CVolumeEvent *,int)

- ea: `0x180018480`
- end: `0x1800185c2`
- name: `?_AdviseVolumeChangeHelper@COMXProc@@YAJPEAVCVolumeEvent@Storage@@H@Z`
- size: `322`
- prototype: `__int64 __fastcall(COMXProc *this, struct Storage::CVolumeEvent *)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180014fd0`

## callees

- `0x180003570`
- `0x180007b04`
- `0x180007b20`
- `0x1800137e0`
- `0x1800153b0`
- `0x1800169e0`
- `0x180018480`
- `0x1800185c8`
- `0x18001b404`
- `0x180029854`
- `0x1800298d8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001859f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001859f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800185ad`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800185ad`

## pseudocode

```c
__int64 __fastcall COMXProc::_AdviseVolumeChangeHelper(COMXProc *this, struct Storage::CVolumeEvent *a2)
{
  CRefCounted *v2; // rsi
  int v4; // ebp
  __int64 v5; // rdi
  int Elem; // ebx
  CRefCounted *v7; // rcx
  COMXProc::CThreadTaskVolumeEvent *v8; // rax
  struct tagVOLUMEINFO2 *v9; // rsi
  COMXProc::CThreadTaskVolumeEvent *v10; // rdi
  int inited; // eax
  HANDLE ProcessHeap; // rax
  CRefCounted *v14; // [rsp+40h] [rbp+8h] BYREF
  LPVOID lpMem; // [rsp+50h] [rbp+18h] BYREF

  v2 = Storage::g_pnelVolumeInfo;
  v4 = (int)a2;
  lpMem = 0;
  v14 = 0;
  v5 = 0;
  CCritSectWithResource<CNamedElemList<PnPServices::CHandleNotif>>::Enter(*((_QWORD *)Storage::g_pnelVolumeInfo + 3));
  Elem = CNamedElemList<Storage::CVolumeInfo>::_GetElemSlot<unsigned short const *>(v2, (char *)this + 16, &v14);
  if ( Elem >= 0 )
  {
    v7 = v14;
    _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)v14 + 2) + 24LL));
    v5 = *((_QWORD *)v7 + 2);
    Elem = 0;
    CRefCounted::Release(v7);
  }
  CCritSectWithResource<CDummyResource>::Leave(*((_QWORD *)v2 + 3));
  if ( Elem >= 0 )
  {
    Elem = Storage::CVolume::GetVOLUMEINFO2((Storage::CVolume *)(v5 + 32), (struct tagVOLUMEINFO2 **)&lpMem);
    CRefCounted::Release((CRefCounted *)(v5 + 16));
    if ( Elem >= 0 )
    {
      v8 = (COMXProc::CThreadTaskVolumeEvent *)operator new(0x38u);
      v9 = (struct tagVOLUMEINFO2 *)lpMem;
      v10 = v8;
      if ( v8 )
      {
        *((_DWORD *)v8 + 2) = 1;
        *((_DWORD *)v8 + 4) = -2147418113;
        *((_QWORD *)v8 + 3) = 0;
        *((_DWORD *)v8 + 8) = 0;
        *((_QWORD *)v8 + 5) = 0;
        *(_QWORD *)v8 = &COMXProc::CThreadTaskVolumeEvent::`vftable';
        Elem = CThreadTaskRegister::RegisterWithService(v8);
        if ( Elem >= 0 )
        {
          if ( v4 )
            inited = COMXProc::CThreadTaskVolumeEvent::InitAdded(v10, v9);
          else
            inited = COMXProc::CThreadTaskVolumeEvent::InitUpdated(v10, v9);
          Elem = inited;
          if ( inited >= 0 )
            Elem = CThreadTask::Run(v10);
        }
        CRefCounted::Release(v10);
      }
      else
      {
        Elem = -2147024882;
      }
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v9);
    }
  }
  return (unsigned int)Elem;
}

```

## disassembly

```asm
0x180018480  mov     [rsp+arg_8], rbx
0x180018485  push    rbp
0x180018486  push    rsi
0x180018487  push    rdi
0x180018488  sub     rsp, 20h
0x18001848c  mov     rsi, cs:?g_pnelVolumeInfo@Storage@@3PEAV?$CNamedElemList@VCVolumeInfo@Storage@@@@EA; CNamedElemList<Storage::CVolumeInfo> * Storage::g_pnelVolumeInfo
0x180018493  mov     rbx, rcx
0x180018496  mov     ebp, edx
0x180018498  mov     [rsp+38h+lpMem], 0
0x1800184a1  mov     [rsp+38h+arg_0], 0
0x1800184aa  xor     edi, edi
0x1800184ac  mov     rcx, [rsi+18h]
0x1800184b0  call    ?Enter@?$CCritSectWithResource@V?$CNamedElemList@VCHandleNotif@PnPServices@@@@@@QEAAXXZ; CCritSectWithResource<CNamedElemList<PnPServices::CHandleNotif>>::Enter(void)
0x1800184b5  lea     rdx, [rbx+10h]
0x1800184b9  mov     rcx, rsi
0x1800184bc  lea     r8, [rsp+38h+arg_0]
0x1800184c1  call    ??$_GetElemSlot@PEBG@?$CNamedElemList@VCVolumeInfo@Storage@@@@AEAAJQEBGPEAPEAV?$CElemSlot@VCVolumeInfo@Storage@@@@@Z; CNamedElemList<Storage::CVolumeInfo>::_GetElemSlot<ushort const *>(ushort const * const,CElemSlot<Storage::CVolumeInfo> * *)
0x1800184c6  mov     ebx, eax
0x1800184c8  test    eax, eax
0x1800184ca  js      short loc_1800184E4
0x1800184cc  mov     rcx, [rsp+38h+arg_0]; this
0x1800184d1  mov     rax, [rcx+10h]
0x1800184d5  lock inc dword ptr [rax+18h]
0x1800184d9  mov     rdi, [rcx+10h]
0x1800184dd  xor     ebx, ebx
0x1800184df  call    ?Release@CRefCounted@@QEBAKXZ; CRefCounted::Release(void)
0x1800184e4  mov     rcx, [rsi+18h]
0x1800184e8  call    ?Leave@?$CCritSectWithResource@VCDummyResource@@@@QEAAXXZ; CCritSectWithResource<CDummyResource>::Leave(void)
0x1800184ed  test    ebx, ebx
0x1800184ef  js      loc_1800185B3
0x1800184f5  lea     rcx, [rdi+20h]; this
0x1800184f9  lea     rdx, [rsp+38h+lpMem]; struct tagVOLUMEINFO2 **
0x1800184fe  call    ?GetVOLUMEINFO2@CVolume@Storage@@QEAAJPEAPEAUtagVOLUMEINFO2@@@Z; Storage::CVolume::GetVOLUMEINFO2(tagVOLUMEINFO2 * *)
0x180018503  lea     rcx, [rdi+10h]; this
0x180018507  mov     ebx, eax
0x180018509  call    ?Release@CRefCounted@@QEBAKXZ; CRefCounted::Release(void)
0x18001850e  test    ebx, ebx
0x180018510  js      loc_1800185B3
0x180018516  mov     ecx, 38h ; '8'; Size
0x18001851b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180018520  mov     rsi, [rsp+38h+lpMem]
0x180018525  mov     rdi, rax
0x180018528  test    rax, rax
0x18001852b  jz      short loc_18001859A
0x18001852d  mov     dword ptr [rax+8], 1
0x180018534  mov     rcx, rdi; this
0x180018537  mov     dword ptr [rax+10h], 8000FFFFh
0x18001853e  mov     qword ptr [rax+18h], 0
0x180018546  mov     dword ptr [rax+20h], 0
0x18001854d  mov     qword ptr [rax+28h], 0
0x180018555  lea     rax, ??_7CThreadTaskVolumeEvent@COMXProc@@6B@; const COMXProc::CThreadTaskVolumeEvent::`vftable'
0x18001855c  mov     [rdi], rax
0x18001855f  call    ?RegisterWithService@CThreadTaskRegister@@QEAAJXZ; CThreadTaskRegister::RegisterWithService(void)
0x180018564  mov     ebx, eax
0x180018566  test    eax, eax
0x180018568  js      short loc_180018590
0x18001856a  mov     rdx, rsi; struct tagVOLUMEINFO2 *
0x18001856d  mov     rcx, rdi; this
0x180018570  test    ebp, ebp
0x180018572  jz      short loc_18001857B
0x180018574  call    ?InitAdded@CThreadTaskVolumeEvent@COMXProc@@QEAAJPEAUtagVOLUMEINFO2@@@Z; COMXProc::CThreadTaskVolumeEvent::InitAdded(tagVOLUMEINFO2 *)
0x180018579  jmp     short loc_180018580
0x18001857b  call    ?InitUpdated@CThreadTaskVolumeEvent@COMXProc@@QEAAJPEAUtagVOLUMEINFO2@@@Z; COMXProc::CThreadTaskVolumeEvent::InitUpdated(tagVOLUMEINFO2 *)
0x180018580  mov     ebx, eax
0x180018582  test    eax, eax
0x180018584  js      short loc_180018590
0x180018586  mov     rcx, rdi; Context
0x180018589  call    ?Run@CThreadTask@@QEAAJXZ; CThreadTask::Run(void)
0x18001858e  mov     ebx, eax
0x180018590  mov     rcx, rdi; this
0x180018593  call    ?Release@CRefCounted@@QEBAKXZ; CRefCounted::Release(void)
0x180018598  jmp     short loc_18001859F
0x18001859a  mov     ebx, 8007000Eh
0x18001859f  call    cs:__imp_GetProcessHeap
0x1800185a5  mov     r8, rsi; lpMem
0x1800185a8  xor     edx, edx; dwFlags
0x1800185aa  mov     rcx, rax; hHeap
0x1800185ad  call    cs:__imp_HeapFree
0x1800185b3  mov     eax, ebx
0x1800185b5  mov     rbx, [rsp+38h+arg_8]
0x1800185ba  add     rsp, 20h
0x1800185be  pop     rdi
0x1800185bf  pop     rsi
0x1800185c0  pop     rbp
0x1800185c1  retn
```
