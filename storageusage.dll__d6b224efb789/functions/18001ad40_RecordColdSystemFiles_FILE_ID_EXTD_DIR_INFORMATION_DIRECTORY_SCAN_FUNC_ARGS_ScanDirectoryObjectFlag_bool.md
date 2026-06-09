# RecordColdSystemFiles(_FILE_ID_EXTD_DIR_INFORMATION *,DIRECTORY_SCAN_FUNC_ARGS *,ScanDirectoryObjectFlag,bool)

- ea: `0x18001ad40`
- end: `0x18001aeba`
- name: `?RecordColdSystemFiles@@YAJPEAU_FILE_ID_EXTD_DIR_INFORMATION@@PEAUDIRECTORY_SCAN_FUNC_ARGS@@W4ScanDirectoryObjectFlag@@_N@Z`
- size: `378`
- prototype: `int __high(struct _FILE_ID_EXTD_DIR_INFORMATION *, struct DIRECTORY_SCAN_FUNC_ARGS *, enum ScanDirectoryObjectFlag, bool)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x1800152d4`
- `0x18001ad40`
- `0x18001aec0`
- `0x18001d608`
- `0x18001d6c0`
- `0x18001dca4`
- `0x18001dfc4`
- `0x18001e58c`
- `0x18001f458`
- `0x180020c30`

## pseudocode

```c
__int64 __fastcall RecordColdSystemFiles(
        union _LARGE_INTEGER *a1,
        struct DIRECTORY_SCAN_FUNC_ARGS *a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v4; // rsi
  __int64 v7; // r9
  __int64 v9; // rdx
  __int64 v10; // r8
  int v11; // eax
  unsigned int v12; // esi
  __int64 v13; // r8
  int v14; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v4 = (unsigned __int8)a4;
  switch ( (_DWORD)a3 )
  {
    case 0x10:
      WriteLATScanBuffer(a2, (__int64)a2, a3);
      WriteFileSizesMap(*((_QWORD *)a2 + 20), *(unsigned int *)a2);
      LOBYTE(v7) = v4;
      RecordDirStats(a1, a2, 16, v7);
      if ( *((_BYTE *)a2 + 700) )
        UploadWERTelemetry(a2);
      break;
    case 8:
      return RecordDirStats(a1, a2, a3, a4);
    case 4:
      if ( CompareTimeThreshold(a1[2], *((_DWORD *)a2 + 174)) == -1 )
      {
        v9 = *((unsigned __int16 *)a2 + 65);
        v10 = (unsigned int)*((unsigned __int16 *)a2 + 8 * v4 + 20) + a1[7].HighPart + 6;
        if ( (unsigned int)v10 <= (unsigned int)v9 )
        {
          if ( *((_WORD *)a2 + 60) >= 0x3E8u || (unsigned int)v10 + *((unsigned __int16 *)a2 + 64) > (unsigned int)v9 )
            WriteLATScanBuffer(a2, v9, v10);
          v11 = CopyPath((__int64)a1, (__int64)a2, 0, v4, 0);
          v12 = v11;
          if ( v11 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x481,
              (unsigned int)"onecore\\drivers\\storage\\storsvc\\storageusage\\storagegrovelerscans.cpp",
              (const char *)(unsigned int)v11,
              v14);
            return v12;
          }
          v13 = *((unsigned __int16 *)a2 + 60);
          *(union _LARGE_INTEGER *)(*((_QWORD *)a2 + 18) + 8 * v13) = a1[5];
          *(union _LARGE_INTEGER *)(*((_QWORD *)a2 + 19) + 8 * v13) = a1[2];
          ++*((_WORD *)a2 + 60);
        }
        else
        {
          ++*((_WORD *)a2 + 40);
        }
      }
      LOBYTE(v9) = 1;
      UpdateLastAccessTimesMap(a1, v9, *((_QWORD *)a2 + 20));
      UpdateFileCountsMap(a1, *((_QWORD *)a2 + 20));
      break;
  }
  return 0;
}

```

## disassembly

```asm
0x18001ad40  mov     [rsp+arg_0], rbx
0x18001ad45  mov     [rsp+arg_8], rsi
0x18001ad4a  push    rdi
0x18001ad4b  sub     rsp, 30h
0x18001ad4f  movzx   esi, r9b
0x18001ad53  mov     rbx, rdx
0x18001ad56  mov     rdi, rcx
0x18001ad59  cmp     r8d, 10h
0x18001ad5d  jnz     short loc_18001ADA3
0x18001ad5f  mov     rcx, rdx; struct DIRECTORY_SCAN_FUNC_ARGS *
0x18001ad62  call    ?WriteLATScanBuffer@@YAXPEAUDIRECTORY_SCAN_FUNC_ARGS@@@Z; WriteLATScanBuffer(DIRECTORY_SCAN_FUNC_ARGS *)
0x18001ad67  mov     edx, [rbx]
0x18001ad69  mov     rcx, [rbx+0A0h]
0x18001ad70  call    ?WriteFileSizesMap@@YAXPEAV?$map@K_KU?$less@K@std@@V?$allocator@U?$pair@$$CBK_K@std@@@2@@std@@W4SCAN_ID@@@Z; WriteFileSizesMap(std::map<ulong,unsigned __int64> *,SCAN_ID)
0x18001ad75  mov     r9b, sil
0x18001ad78  mov     r8d, 10h
0x18001ad7e  mov     rdx, rbx
0x18001ad81  mov     rcx, rdi
0x18001ad84  call    ?RecordDirStats@@YAJPEAU_FILE_ID_EXTD_DIR_INFORMATION@@PEAUDIRECTORY_SCAN_FUNC_ARGS@@W4ScanDirectoryObjectFlag@@_N@Z; RecordDirStats(_FILE_ID_EXTD_DIR_INFORMATION *,DIRECTORY_SCAN_FUNC_ARGS *,ScanDirectoryObjectFlag,bool)
0x18001ad89  cmp     byte ptr [rbx+2BCh], 0
0x18001ad90  jz      loc_18001AEA8
0x18001ad96  mov     rcx, rbx; struct DIRECTORY_SCAN_FUNC_ARGS *
0x18001ad99  call    ?UploadWERTelemetry@@YAJPEAUDIRECTORY_SCAN_FUNC_ARGS@@@Z; UploadWERTelemetry(DIRECTORY_SCAN_FUNC_ARGS *)
0x18001ad9e  jmp     loc_18001AEA8
0x18001ada3  cmp     r8d, 8
0x18001ada7  jnz     short loc_18001ADB6
0x18001ada9  mov     r9b, sil
0x18001adac  call    ?RecordDirStats@@YAJPEAU_FILE_ID_EXTD_DIR_INFORMATION@@PEAUDIRECTORY_SCAN_FUNC_ARGS@@W4ScanDirectoryObjectFlag@@_N@Z; RecordDirStats(_FILE_ID_EXTD_DIR_INFORMATION *,DIRECTORY_SCAN_FUNC_ARGS *,ScanDirectoryObjectFlag,bool)
0x18001adb1  jmp     loc_18001AEAA
0x18001adb6  cmp     r8d, 4
0x18001adba  jnz     loc_18001AEA8
0x18001adc0  mov     edx, [rdx+2B8h]; unsigned int
0x18001adc6  mov     rcx, [rcx+10h]; union _LARGE_INTEGER
0x18001adca  call    ?CompareTimeThreshold@@YAJT_LARGE_INTEGER@@K@Z; CompareTimeThreshold(_LARGE_INTEGER,ulong)
0x18001adcf  cmp     eax, 0FFFFFFFFh
0x18001add2  jnz     loc_18001AE88
0x18001add8  mov     r8d, [rdi+3Ch]
0x18001addc  mov     rax, rsi
0x18001addf  movzx   edx, word ptr [rbx+82h]
0x18001ade6  add     rax, rax
0x18001ade9  add     r8d, 6
0x18001aded  movzx   ecx, word ptr [rbx+rax*8+28h]
0x18001adf2  add     r8d, ecx
0x18001adf5  cmp     r8d, edx
0x18001adf8  jbe     short loc_18001AE03
0x18001adfa  inc     word ptr [rbx+50h]
0x18001adfe  jmp     loc_18001AE88
0x18001ae03  mov     eax, 3E8h
0x18001ae08  cmp     [rbx+78h], ax
0x18001ae0c  jnb     short loc_18001AE1C
0x18001ae0e  movzx   eax, word ptr [rbx+80h]
0x18001ae15  add     eax, r8d
0x18001ae18  cmp     eax, edx
0x18001ae1a  jbe     short loc_18001AE24
0x18001ae1c  mov     rcx, rbx; struct DIRECTORY_SCAN_FUNC_ARGS *
0x18001ae1f  call    ?WriteLATScanBuffer@@YAXPEAUDIRECTORY_SCAN_FUNC_ARGS@@@Z; WriteLATScanBuffer(DIRECTORY_SCAN_FUNC_ARGS *)
0x18001ae24  mov     r9b, sil
0x18001ae27  mov     qword ptr [rsp+38h+var_18], 0; int
0x18001ae30  xor     r8d, r8d
0x18001ae33  mov     rdx, rbx
0x18001ae36  mov     rcx, rdi
0x18001ae39  call    ?CopyPath@@YAJPEAU_FILE_ID_EXTD_DIR_INFORMATION@@PEAUDIRECTORY_SCAN_FUNC_ARGS@@W4PATH_TYPE@@_NPEBG@Z; CopyPath(_FILE_ID_EXTD_DIR_INFORMATION *,DIRECTORY_SCAN_FUNC_ARGS *,PATH_TYPE,bool,ushort const *)
0x18001ae3e  mov     esi, eax
0x18001ae40  test    eax, eax
0x18001ae42  jns     short loc_18001AE61
0x18001ae44  mov     rcx, [rsp+38h]; this
0x18001ae49  lea     r8, aOnecoreDrivers; "onecore\\drivers\\storage\\storsvc\\sto"...
0x18001ae50  mov     r9d, eax; char *
0x18001ae53  mov     edx, 481h; void *
0x18001ae58  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ae5d  mov     eax, esi
0x18001ae5f  jmp     short loc_18001AEAA
0x18001ae61  mov     rax, [rdi+28h]
0x18001ae65  movzx   r8d, word ptr [rbx+78h]
0x18001ae6a  mov     rcx, [rbx+90h]
0x18001ae71  mov     [rcx+r8*8], rax
0x18001ae75  mov     rax, [rdi+10h]
0x18001ae79  mov     rcx, [rbx+98h]
0x18001ae80  mov     [rcx+r8*8], rax
0x18001ae84  inc     word ptr [rbx+78h]
0x18001ae88  mov     r8, [rbx+0A0h]
0x18001ae8f  mov     dl, 1
0x18001ae91  mov     rcx, rdi
0x18001ae94  call    ?UpdateLastAccessTimesMap@@YAXPEAU_FILE_ID_EXTD_DIR_INFORMATION@@EPEAV?$map@K_KU?$less@K@std@@V?$allocator@U?$pair@$$CBK_K@std@@@2@@std@@@Z; UpdateLastAccessTimesMap(_FILE_ID_EXTD_DIR_INFORMATION *,uchar,std::map<ulong,unsigned __int64> *)
0x18001ae99  mov     rdx, [rbx+0A0h]
0x18001aea0  mov     rcx, rdi
0x18001aea3  call    ?UpdateFileCountsMap@@YAXPEAU_FILE_ID_EXTD_DIR_INFORMATION@@PEAV?$map@K_KU?$less@K@std@@V?$allocator@U?$pair@$$CBK_K@std@@@2@@std@@@Z; UpdateFileCountsMap(_FILE_ID_EXTD_DIR_INFORMATION *,std::map<ulong,unsigned __int64> *)
0x18001aea8  xor     eax, eax
0x18001aeaa  mov     rbx, [rsp+38h+arg_0]
0x18001aeaf  mov     rsi, [rsp+38h+arg_8]
0x18001aeb4  add     rsp, 30h
0x18001aeb8  pop     rdi
0x18001aeb9  retn
```
