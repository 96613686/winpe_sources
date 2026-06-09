# InternetMapError(ulong)

- ea: `0x18008da14`
- end: `0x18008ecb0`
- name: `?InternetMapError@@YAPEADK@Z`
- size: `4764`
- prototype: `char *__fastcall(unsigned int)`
- caller_count: `37`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800141e0`
- `0x180015aa0`
- `0x180015bd0`
- `0x180015d30`
- `0x180018820`
- `0x1800252ac`
- `0x18002a910`
- `0x18002d250`
- `0x18002ef48`
- `0x1800334f4`
- `0x18003460c`
- `0x1800364d0`
- `0x180037b20`
- `0x180037d40`
- `0x180038e30`
- `0x180039160`
- `0x180045b18`
- `0x180072cac`
- `0x180072f54`
- `0x180075db8`
- `0x1800880d4`
- `0x180096560`
- `0x180096720`
- `0x1800967f0`
- `0x1800969c0`
- `0x180096af0`
- `0x180096fe0`
- `0x180097494`
- `0x180097678`
- `0x180097710`
- `0x1800977d4`
- `0x1800978fc`
- `0x180097a3c`
- `0x18009baec`
- `0x1800ae828`
- `0x1800aec00`
- `0x1800b12bc`

## callees

- `0x18008da14`

## string_xrefs

- `0x18008da99`: `ERROR_PATH_NOT_FOUND`
- `0x18008da89`: `ERROR_ACCESS_DENIED`
- `0x18008da91`: `ERROR_TOO_MANY_OPEN_FILES`
- `0x18008daeb`: `ERROR_INVALID_ACCESS`
- `0x18008db64`: `ERROR_CURRENT_DIRECTORY`
- `0x18008db4c`: `ERROR_WRITE_PROTECT`
- `0x18008db74`: `ERROR_NOT_READY`
- `0x18008dbc6`: `ERROR_BAD_COMMAND`
- `0x18008dc36`: `ERROR_WRITE_FAULT`
- `0x18008dc2e`: `ERROR_READ_FAULT`
- `0x18008dc68`: `ERROR_BAD_NETPATH`
- `0x18008dd33`: `ERROR_NETWORK_ACCESS_DENIED`
- `0x18008dd3b`: `ERROR_NETNAME_DELETED`
- `0x18008de31`: `ERROR_ALREADY_ASSIGNED`
- `0x18008de19`: `ERROR_NET_WRITE_FAULT`
- `0x18008de39`: `ERROR_EXCL_SEM_ALREADY_OWNED`
- `0x18008dee4`: `ERROR_OPEN_FAILED`
- `0x18008df9a`: `ERROR_CHILD_NOT_COMPLETE`
- `0x18008df92`: `ERROR_DIRECT_ACCESS_HANDLE`
- `0x18008e00a`: `ERROR_PATH_BUSY`
- `0x18008e06f`: `ERROR_BAD_PATHNAME`
- `0x18008e057`: `ERROR_ALREADY_EXISTS`
- `0x18008e170`: `ERROR_PARTIAL_COPY`
- `0x18008e1e3`: `ERROR_IO_INCOMPLETE`
- `0x18008e1d3`: `ERROR_NOACCESS`
- `0x18008e250`: `ERROR_NO_TOKEN`
- `0x18008e238`: `ERROR_CANTOPEN`
- `0x18008e260`: `ERROR_CANTWRITE`
- `0x18008e230`: `ERROR_CANTREAD`
- `0x18008e2cb`: `ERROR_REGISTRY_CORRUPT`
- `0x18008e2d3`: `ERROR_REGISTRY_RECOVERED`
- `0x18008e2bb`: `ERROR_NOT_REGISTRY_FILE`
- `0x18008e2c3`: `ERROR_REGISTRY_IO_FAILED`
- `0x18008e2b3`: `ERROR_KEY_DELETED`
- `0x18008e333`: `ERROR_DLL_INIT_FAILED`
- `0x18008e2db`: `ERROR_SERVICE_NOT_ACTIVE`
- `0x18008e087`: `WAIT_IO_COMPLETION`
- `0x18008e3f8`: `RPC_S_ALREADY_REGISTERED`
- `0x18008e3e8`: `RPC_S_ALREADY_LISTENING`
- `0x18008e3f0`: `RPC_S_TYPE_ALREADY_REGISTERED`
- `0x18008e43a`: `RPC_S_CANT_CREATE_ENDPOINT`
- `0x18008e47a`: `RPC_S_PROTOCOL_ERROR`
- `0x18008e4fa`: `RPC_S_UNKNOWN_AUTHN_SERVICE`
- `0x18008e512`: `RPC_S_UNKNOWN_AUTHZ_SERVICE`
- `0x18008e53a`: `RPC_S_INCOMPLETE_NAME`
- `0x18008e562`: `RPC_S_ENTRY_ALREADY_EXISTS`
- `0x18008e572`: `RPC_S_NAME_SERVICE_UNAVAILABLE`
- `0x18008e5ca`: `RPC_X_SS_CHAR_TRANS_OPEN_FAIL`
- `0x18008eaf0`: `ERROR_WINHTTP_HEADER_ALREADY_EXISTS`
- `0x18008ebc8`: `SEC_E_CANNOT_INSTALL`
- `0x18008ec04`: `SEC_E_INVALID_TOKEN`
- `0x18008ec3a`: `SEC_E_NO_IMPERSONATION`
- `0x18008eb90`: `SEC_I_COMPLETE_NEEDED`
- `0x18008eb88`: `SEC_I_COMPLETE_AND_CONTINUE`
- `0x18008ec82`: `SEC_E_INCOMPLETE_MESSAGE`
- `0x18008e738`: `WSAEALREADY`
- `0x18008e8cb`: `WSAENOTEMPTY`
- `0x18008e923`: `WSASYSNOTREADY`

## pseudocode

```c
char *__fastcall InternetMapError(unsigned int a1)
{
  unsigned int v1; // ecx
  unsigned int v2; // ecx
  unsigned int v3; // ecx
  unsigned int v4; // ecx
  unsigned int v5; // ecx
  char *result; // rax
  unsigned int v7; // ecx
  unsigned int v8; // ecx
  unsigned int v9; // ecx
  unsigned int v10; // ecx
  unsigned int v11; // ecx
  unsigned int v12; // ecx
  unsigned int v13; // ecx
  unsigned int v14; // ecx
  unsigned int v15; // ecx
  unsigned int v16; // ecx
  unsigned int v17; // ecx
  unsigned int v18; // ecx
  unsigned int v19; // ecx
  unsigned int v20; // ecx
  unsigned int v21; // ecx
  unsigned int v22; // ecx
  unsigned int v23; // ecx
  unsigned int v24; // ecx
  unsigned int v25; // ecx
  unsigned int v26; // ecx
  unsigned int v27; // ecx
  unsigned int v28; // ecx
  unsigned int v29; // ecx
  unsigned int v30; // ecx
  unsigned int v31; // ecx
  unsigned int v32; // ecx
  unsigned int v33; // ecx
  unsigned int v34; // ecx
  unsigned int v35; // ecx
  unsigned int v36; // ecx
  unsigned int v37; // ecx
  unsigned int v38; // ecx
  unsigned int v39; // ecx
  unsigned int v40; // ecx
  unsigned int v41; // ecx
  unsigned int v42; // ecx
  unsigned int v43; // ecx
  unsigned int v44; // ecx
  unsigned int v45; // ecx
  unsigned int v46; // ecx
  unsigned int v47; // ecx
  unsigned int v48; // ecx
  unsigned int v49; // ecx
  unsigned int v50; // ecx
  unsigned int v51; // ecx
  unsigned int v52; // ecx
  unsigned int v53; // ecx
  unsigned int v54; // ecx
  unsigned int v55; // ecx
  unsigned int v56; // ecx
  unsigned int v57; // ecx
  unsigned int v58; // ecx
  unsigned int v59; // ecx
  unsigned int v60; // ecx
  unsigned int v61; // ecx
  unsigned int v62; // ecx
  unsigned int v63; // ecx
  unsigned int v64; // ecx
  unsigned int v65; // ecx
  unsigned int v66; // ecx
  unsigned int v67; // ecx
  unsigned int v68; // ecx
  unsigned int v69; // ecx
  unsigned int v70; // ecx
  unsigned int v71; // ecx
  unsigned int v72; // ecx
  unsigned int v73; // ecx
  unsigned int v74; // ecx
  unsigned int v75; // ecx
  unsigned int v76; // ecx
  unsigned int v77; // ecx
  unsigned int v78; // ecx
  unsigned int v79; // ecx
  unsigned int v80; // ecx
  unsigned int v81; // ecx
  unsigned int v82; // ecx
  unsigned int v83; // ecx
  unsigned int v84; // ecx
  unsigned int v85; // ecx
  unsigned int v86; // ecx
  unsigned int v87; // ecx
  unsigned int v88; // ecx
  unsigned int v89; // ecx
  unsigned int v90; // ecx
  unsigned int v91; // ecx
  unsigned int v92; // ecx
  unsigned int v93; // ecx
  unsigned int v94; // ecx
  unsigned int v95; // ecx
  unsigned int v96; // ecx
  unsigned int v97; // ecx
  unsigned int v98; // ecx
  unsigned int v99; // ecx
  unsigned int v100; // ecx
  unsigned int v101; // ecx
  unsigned int v102; // ecx
  unsigned int v103; // ecx
  unsigned int v104; // ecx
  unsigned int v105; // ecx
  unsigned int v106; // ecx
  unsigned int v107; // ecx
  unsigned int v108; // ecx
  unsigned int v109; // ecx
  unsigned int v110; // ecx
  unsigned int v111; // ecx
  unsigned int v112; // ecx
  unsigned int v113; // ecx
  unsigned int v114; // ecx
  unsigned int v115; // ecx
  unsigned int v116; // ecx
  unsigned int v117; // ecx
  unsigned int v118; // ecx
  unsigned int v119; // ecx
  unsigned int v120; // ecx
  unsigned int v121; // ecx
  unsigned int v122; // ecx
  unsigned int v123; // ecx
  unsigned int v124; // ecx
  unsigned int v125; // ecx
  unsigned int v126; // ecx
  unsigned int v127; // ecx
  unsigned int v128; // ecx
  unsigned int v129; // ecx
  unsigned int v130; // ecx
  unsigned int v131; // ecx
  unsigned int v132; // ecx
  unsigned int v133; // ecx
  unsigned int v134; // ecx
  unsigned int v135; // ecx
  unsigned int v136; // ecx
  unsigned int v137; // ecx
  unsigned int v138; // ecx
  unsigned int v139; // ecx
  unsigned int v140; // ecx
  unsigned int v141; // ecx
  unsigned int v142; // ecx
  unsigned int v143; // ecx
  unsigned int v144; // ecx
  unsigned int v145; // ecx
  unsigned int v146; // ecx
  unsigned int v147; // ecx
  unsigned int v148; // ecx
  unsigned int v149; // ecx
  unsigned int v150; // ecx
  unsigned int v151; // ecx
  unsigned int v152; // ecx
  unsigned int v153; // ecx
  unsigned int v154; // ecx
  unsigned int v155; // ecx
  unsigned int v156; // ecx
  unsigned int v157; // ecx
  unsigned int v158; // ecx
  unsigned int v159; // ecx
  unsigned int v160; // ecx
  const char *v161; // rax
  bool v162; // zf
  unsigned int v163; // ecx
  unsigned int v164; // ecx
  unsigned int v165; // ecx
  unsigned int v166; // ecx
  unsigned int v167; // ecx
  unsigned int v168; // ecx
  unsigned int v169; // ecx
  unsigned int v170; // ecx
  unsigned int v171; // ecx
  unsigned int v172; // ecx
  unsigned int v173; // ecx
  unsigned int v174; // ecx
  unsigned int v175; // ecx
  unsigned int v176; // ecx
  unsigned int v177; // ecx
  unsigned int v178; // ecx
  unsigned int v179; // ecx
  unsigned int v180; // ecx
  unsigned int v181; // ecx
  unsigned int v182; // ecx
  const char *v183; // rdx

  if ( a1 <= 0xC0 )
  {
    if ( a1 == 192 )
      return "WAIT_IO_COMPLETION";
    if ( a1 > 0x44 )
    {
      if ( a1 > 0x75 )
      {
        if ( a1 > 0x83 )
        {
          if ( a1 > 0x98 )
          {
            v78 = a1 - 153;
            if ( !v78 )
              return "ERROR_INVALID_LIST_FORMAT";
            v79 = v78 - 7;
            if ( !v79 )
              return "ERROR_BAD_ARGUMENTS";
            v80 = v79 - 1;
            if ( !v80 )
              return "ERROR_BAD_PATHNAME";
            v81 = v80 - 9;
            if ( !v81 )
              return "ERROR_BUSY";
            v82 = v81 - 3;
            if ( !v82 )
              return "ERROR_CANCEL_VIOLATION";
            if ( v82 == 10 )
              return "ERROR_ALREADY_EXISTS";
          }
          else
          {
            if ( a1 == 152 )
              return "ERROR_TOO_MANY_MUXWAITERS";
            v73 = a1 - 132;
            if ( !v73 )
              return "ERROR_SEEK_ON_DEVICE";
            v74 = v73 - 12;
            if ( !v74 )
              return "ERROR_DIR_NOT_ROOT";
            v75 = v74 - 1;
            if ( !v75 )
              return "ERROR_DIR_NOT_EMPTY";
            v76 = v75 - 3;
            if ( !v76 )
              return "ERROR_PATH_BUSY";
            v77 = v76 - 2;
            if ( !v77 )
              return "ERROR_SYSTEM_TRACE";
            if ( v77 == 1 )
              return "ERROR_INVALID_EVENT_COUNT";
          }
        }
        else
        {
          if ( a1 == 131 )
            return "ERROR_NEGATIVE_SEEK";
          if ( a1 > 0x7C )
          {
            v68 = a1 - 125;
            if ( !v68 )
              return "ERROR_NO_VOLUME_LABEL";
            v69 = v68 - 1;
            if ( !v69 )
              return "ERROR_MOD_NOT_FOUND";
            v70 = v69 - 1;
            if ( !v70 )
              return "ERROR_PROC_NOT_FOUND";
            v71 = v70 - 1;
            if ( !v71 )
              return "ERROR_WAIT_NO_CHILDREN";
            v72 = v71 - 1;
            if ( !v72 )
              return "ERROR_CHILD_NOT_COMPLETE";
            if ( v72 == 1 )
              return "ERROR_DIRECT_ACCESS_HANDLE";
          }
          else
          {
            if ( a1 == 124 )
              return "ERROR_INVALID_LEVEL";
            v63 = a1 - 118;
            if ( !v63 )
              return "ERROR_INVALID_VERIFY_SWITCH";
            v64 = v63 - 1;
            if ( !v64 )
              return "ERROR_BAD_DRIVER_LEVEL";
            v65 = v64 - 1;
            if ( !v65 )
              return "ERROR_CALL_NOT_IMPLEMENTED";
            v66 = v65 - 1;
            if ( !v66 )
              return "ERROR_SEM_TIMEOUT";
            v67 = v66 - 1;
            if ( !v67 )
              return "ERROR_INSUFFICIENT_BUFFER";
            if ( v67 == 1 )
              return "ERROR_INVALID_NAME";
          }
        }
      }
      else
      {
        if ( a1 == 117 )
          return "ERROR_INVALID_CATEGORY";
        if ( a1 > 0x65 )
        {
          if ( a1 > 0x6C )
          {
            v58 = a1 - 109;
            if ( !v58 )
              return "ERROR_BROKEN_PIPE";
            v59 = v58 - 1;
            if ( !v59 )
              return "ERROR_OPEN_FAILED";
            v60 = v59 - 1;
            if ( !v60 )
              return "ERROR_BUFFER_OVERFLOW";
            v61 = v60 - 1;
            if ( !v61 )
              return "ERROR_DISK_FULL";
            v62 = v61 - 1;
            if ( !v62 )
              return "ERROR_NO_MORE_SEARCH_HANDLES";
            if ( v62 == 1 )
              return "ERROR_INVALID_TARGET_HANDLE";
          }
          else
          {
            if ( a1 == 108 )
              return "ERROR_DRIVE_LOCKED";
            v53 = a1 - 102;
            if ( !v53 )
              return "ERROR_SEM_IS_SET";
            v54 = v53 - 1;
            if ( !v54 )
              return "ERROR_TOO_MANY_SEM_REQUESTS";
            v55 = v54 - 1;
            if ( !v55 )
              return "ERROR_INVALID_AT_INTERRUPT_TIME";
            v56 = v55 - 1;
            if ( !v56 )
              return "ERROR_SEM_OWNER_DIED";
            v57 = v56 - 1;
            if ( !v57 )
              return "ERROR_SEM_USER_LIMIT";
            if ( v57 == 1 )
              return "ERROR_DISK_CHANGE";
          }
        }
        else
        {
          if ( a1 == 101 )
            return "ERROR_EXCL_SEM_ALREADY_OWNED";
          if ( a1 > 0x54 )
          {
            v48 = a1 - 85;
            if ( !v48 )
              return "ERROR_ALREADY_ASSIGNED";
            v49 = v48 - 1;
            if ( !v49 )
              return "ERROR_INVALID_PASSWORD";
            v50 = v49 - 1;
            if ( !v50 )
              return "ERROR_INVALID_PARAMETER";
            v51 = v50 - 1;
            if ( !v51 )
              return "ERROR_NET_WRITE_FAULT";
            v52 = v51 - 1;
            if ( !v52 )
              return "ERROR_NO_PROC_SLOTS";
            if ( v52 == 11 )
              return "ERROR_TOO_MANY_SEMAPHORES";
          }
          else
          {
            if ( a1 == 84 )
              return "ERROR_OUT_OF_STRUCTURES";
            v42 = a1 - 69;
            if ( !v42 )
              return "ERROR_TOO_MANY_SESS";
            v43 = v42 - 1;
            if ( !v43 )
              return "ERROR_SHARING_PAUSED";
            v44 = v43 - 1;
            if ( !v44 )
              return "ERROR_REQ_NOT_ACCEP";
            v45 = v44 - 1;
            if ( !v45 )
              return "ERROR_REDIR_PAUSED";
            v46 = v45 - 8;
            if ( !v46 )
              return "ERROR_FILE_EXISTS";
            v47 = v46 - 2;
            if ( !v47 )
              return "ERROR_CANNOT_MAKE";
            if ( v47 == 1 )
              return "ERROR_FAIL_I24";
          }
        }
      }
    }
    else
    {
      if ( a1 == 68 )
        return "ERROR_TOO_MANY_NAMES";
      if ( a1 > 0x1C )
      {
        if ( a1 > 0x36 )
        {
          if ( a1 > 0x3D )
          {
            v37 = a1 - 62;
            if ( !v37 )
              return "ERROR_NO_SPOOL_SPACE";
            v38 = v37 - 1;
            if ( !v38 )
              return "ERROR_PRINT_CANCELLED";
            v39 = v38 - 1;
            if ( !v39 )
              return "ERROR_NETNAME_DELETED";
            v40 = v39 - 1;
            if ( !v40 )
              return "ERROR_NETWORK_ACCESS_DENIED";
            v41 = v40 - 1;
            if ( !v41 )
              return "ERROR_BAD_DEV_TYPE";
            if ( v41 == 1 )
              return "ERROR_BAD_NET_NAME";
          }
          else
          {
            if ( a1 == 61 )
              return "ERROR_PRINTQ_FULL";
            v32 = a1 - 55;
            if ( !v32 )
              return "ERROR_DEV_NOT_EXIST";
            v33 = v32 - 1;
            if ( !v33 )
              return "ERROR_TOO_MANY_CMDS";
            v34 = v33 - 1;
            if ( !v34 )
              return "ERROR_ADAP_HDW_ERR";
            v35 = v34 - 1;
            if ( !v35 )
              return "ERROR_BAD_NET_RESP";
            v36 = v35 - 1;
            if ( !v36 )
              return "ERROR_UNEXP_NET_ERR";
            if ( v36 == 1 )
              return "ERROR_BAD_REM_ADAP";
          }
        }
        else
        {
          if ( a1 == 54 )
            return "ERROR_NETWORK_BUSY";
          if ( a1 > 0x24 )
          {
            v27 = a1 - 38;
            if ( !v27 )
              return "ERROR_HANDLE_EOF";
            v28 = v27 - 1;
            if ( !v28 )
              return "ERROR_HANDLE_DISK_FULL";
            v29 = v28 - 11;
            if ( !v29 )
              return "ERROR_NOT_SUPPORTED";
            v30 = v29 - 1;
            if ( !v30 )
              return "ERROR_REM_NOT_LIST";
            v31 = v30 - 1;
            if ( !v31 )
              return "ERROR_DUP_NAME";
            if ( v31 == 1 )
              return "ERROR_BAD_NETPATH";
          }
          else
          {
            if ( a1 == 36 )
              return "ERROR_SHARING_BUFFER_EXCEEDED";
            v22 = a1 - 29;
            if ( !v22 )
              return "ERROR_WRITE_FAULT";
            v23 = v22 - 1;
            if ( !v23 )
              return "ERROR_READ_FAULT";
            v24 = v23 - 1;
            if ( !v24 )
              return "ERROR_GEN_FAILURE";
            v25 = v24 - 1;
            if ( !v25 )
              return "ERROR_SHARING_VIOLATION";
            v26 = v25 - 1;
            if ( !v26 )
              return "ERROR_LOCK_VIOLATION";
            if ( v26 == 1 )
              return "ERROR_WRONG_DISK";
          }
        }
      }
      else
      {
        if ( a1 == 28 )
          return "ERROR_OUT_OF_PAPER";
        if ( a1 > 0xE )
        {
          if ( a1 > 0x15 )
          {
            v17 = a1 - 22;
            if ( !v17 )
              return "ERROR_BAD_COMMAND";
            v18 = v17 - 1;
            if ( !v18 )
              return "ERROR_CRC";
            v19 = v18 - 1;
            if ( !v19 )
              return "ERROR_BAD_LENGTH";
            v20 = v19 - 1;
            if ( !v20 )
              return "ERROR_SEEK";
            v21 = v20 - 1;
            if ( !v21 )
              return "ERROR_NOT_DOS_DISK";
            if ( v21 == 1 )
              return "ERROR_SECTOR_NOT_FOUND";
          }
          else
          {
            if ( a1 == 21 )
              return "ERROR_NOT_READY";
            v12 = a1 - 15;
            if ( !v12 )
              return "ERROR_INVALID_DRIVE";
            v13 = v12 - 1;
            if ( !v13 )
              return "ERROR_CURRENT_DIRECTORY";
            v14 = v13 - 1;
            if ( !v14 )
              return "ERROR_NOT_SAME_DEVICE";
            v15 = v14 - 1;
            if ( !v15 )
              return "ERROR_NO_MORE_FILES";
            v16 = v15 - 1;
            if ( !v16 )
              return "ERROR_WRITE_PROTECT";
            if ( v16 == 1 )
              return "ERROR_BAD_UNIT";
          }
        }
        else
        {
          if ( a1 == 14 )
            return "ERROR_OUTOFMEMORY";
          if ( a1 > 7 )
          {
            v7 = a1 - 8;
            if ( !v7 )
              return "ERROR_NOT_ENOUGH_MEMORY";
            v8 = v7 - 1;
            if ( !v8 )
              return "ERROR_INVALID_BLOCK";
            v9 = v8 - 1;
            if ( !v9 )
              return "ERROR_BAD_ENVIRONMENT";
            v10 = v9 - 1;
            if ( !v10 )
              return "ERROR_BAD_FORMAT";
            v11 = v10 - 1;
            if ( !v11 )
              return "ERROR_INVALID_ACCESS";
            if ( v11 == 1 )
              return "ERROR_INVALID_DATA";
          }
          else
          {
            if ( a1 == 7 )
              return "ERROR_ARENA_TRASHED";
            if ( !a1 )
              return "ERROR_SUCCESS";
            v1 = a1 - 1;
            if ( !v1 )
              return "ERROR_INVALID_FUNCTION";
            v2 = v1 - 1;
            if ( !v2 )
              return "ERROR_FILE_NOT_FOUND";
            v3 = v2 - 1;
            if ( !v3 )
              return "ERROR_PATH_NOT_FOUND";
            v4 = v3 - 1;
            if ( !v4 )
              return "ERROR_TOO_MANY_OPEN_FILES";
            v5 = v4 - 1;
            if ( !v5 )
              return "ERROR_ACCESS_DENIED";
            if ( v5 == 1 )
              return "ERROR_INVALID_HANDLE";
          }
        }
      }
    }
    return "?";
  }
  if ( a1 > 0x6F1 )
  {
    if ( a1 > 0x2AFA )
    {
      if ( a1 <= 0x2F8F )
      {
        if ( a1 == 12175 )
          return "ERROR_WINHTTP_SECURE_FAILURE";
        if ( a1 > 0x2EF1 )
        {
          if ( a1 > 0x2F76 )
          {
            v178 = a1 - 12152;
            if ( !v178 )
              return "ERROR_WINHTTP_INVALID_SERVER_RESPONSE";
            v179 = v178 - 2;
            if ( !v179 )
              return "ERROR_WINHTTP_INVALID_QUERY_REQUEST";
            v180 = v179 - 1;
            if ( !v180 )
              return "ERROR_WINHTTP_HEADER_ALREADY_EXISTS";
            v181 = v180 - 1;
            if ( !v181 )
              return "ERROR_WINHTTP_REDIRECT_FAILED";
            v182 = v181 - 4;
            if ( !v182 )
              return "ERROR_WINHTTP_NOT_REDIRECTED";
            if ( v182 == 12 )
              return "ERROR_WINHTTP_NOT_INITIALIZED";
          }
          else
          {
            if ( a1 == 12150 )
              return "ERROR_WINHTTP_HEADER_NOT_FOUND";
            v173 = a1 - 12018;
            if ( !v173 )
              return "ERROR_WINHTTP_INCORRECT_HANDLE_TYPE";
            v174 = v173 - 1;
            if ( !v174 )
              return "ERROR_WINHTTP_INCORRECT_HANDLE_STATE";
            v175 = v174 - 10;
            if ( !v175 )
              return "ERROR_WINHTTP_CANNOT_CONNECT";
            v176 = v175 - 1;
            if ( !v176 )
              return "ERROR_WINHTTP_CONNECTION_ERROR";
            v177 = v176 - 2;
            if ( !v177 )
              return "ERROR_WINHTTP_RESEND_REQUEST";
            if ( v177 == 12 )
              return "ERROR_WINHTTP_CLIENT_AUTH_CERT_NEEDED";
          }
        }
        else
        {
          if ( a1 == 12017 )
            return "ERROR_WINHTTP_OPERATION_CANCELLED";
          if ( a1 > 0x2EE6 )
          {
            v168 = a1 - 12007;
            if ( !v168 )
              return "ERROR_WINHTTP_NAME_NOT_RESOLVED";
            v169 = v168 - 2;
            if ( !v169 )
              return "ERROR_WINHTTP_INVALID_OPTION";
            v170 = v169 - 2;
            if ( !v170 )
              return "ERROR_WINHTTP_OPTION_NOT_SETTABLE";
            v171 = v170 - 1;
            if ( !v171 )
              return "ERROR_WINHTTP_SHUTDOWN";
            v172 = v171 - 2;
            if ( !v172 )
              return "ERROR_WINHTTP_INCORRECT_PASSWORD";
            if ( v172 == 1 )
              return "ERROR_WINHTTP_LOGIN_FAILURE";
          }
          else
          {
            if ( a1 == 12006 )
              return "ERROR_WINHTTP_UNRECOGNIZED_SCHEME";
            v163 = a1 - 11003;
            if ( !v163 )
              return "WSANO_RECOVERY";
            v164 = v163 - 1;
            if ( !v164 )
              return "WSANO_DATA";
            v165 = v164 - 997;
            if ( !v165 )
              return "ERROR_WINHTTP_OUT_OF_HANDLES";
            v166 = v165 - 1;
            if ( !v166 )
              return "ERROR_WINHTTP_TIMEOUT";
            v167 = v166 - 2;
            if ( !v167 )
              return "ERROR_WINHTTP_INTERNAL_ERROR";
            if ( v167 == 1 )
              return "ERROR_WINHTTP_INVALID_URL";
          }
        }
        return "?";
      }
      if ( a1 > 0x80090330 )
      {
        result = "WAIT_FAILED";
        if ( a1 != -1 )
          return "?";
        return result;
      }
      if ( a1 == -2146893008 )
        return "SEC_E_DECRYPT_FAILURE";
      if ( a1 > 0x80090308 )
      {
        switch ( a1 )
        {
          case 0x80090309:
            result = "SEC_E_CANNOT_PACK";
            break;
          case 0x8009030A:
            result = "SEC_E_QOP_NOT_SUPPORTED";
            break;
          case 0x8009030B:
            result = "SEC_E_NO_IMPERSONATION";
            break;
          case 0x8009030C:
            result = "SEC_E_LOGON_DENIED";
            break;
          case 0x8009030D:
            result = "SEC_E_UNKNOWN_CREDENTIALS";
            break;
          case 0x8009030E:
            result = "SEC_E_NO_CREDENTIALS";
            break;
          case 0x8009030F:
            result = "SEC_E_MESSAGE_ALTERED";
            break;
          case 0x80090310:
            result = "SEC_E_OUT_OF_SEQUENCE";
            break;
          case 0x80090311:
            result = "SEC_E_NO_AUTHENTICATING_AUTHORITY";
            break;
          case 0x80090316:
            result = "SEC_E_BAD_PKGID";
            break;
          case 0x80090317:
            result = "SEC_E_CONTEXT_EXPIRED";
            break;
          case 0x80090318:
            result = "SEC_E_INCOMPLETE_MESSAGE";
            break;
          default:
            return "?";
        }
        return result;
      }
      if ( a1 == -2146893048 )
        return "SEC_E_INVALID_TOKEN";
      if ( a1 > 0x80090302 )
      {
        switch ( a1 )
        {
          case 0x80090303:
            return "SEC_E_TARGET_UNKNOWN";
          case 0x80090304:
            return "SEC_E_INTERNAL_ERROR";
          case 0x80090305:
            return "SEC_E_SECPKG_NOT_FOUND";
          case 0x80090306:
            return "SEC_E_NOT_OWNER";
        }
        v161 = "SEC_E_CANNOT_INSTALL";
        v162 = a1 == -2146893049;
      }
      else
      {
        switch ( a1 )
        {
          case 0x80090302:
            return "SEC_E_UNSUPPORTED_FUNCTION";
          case 0x90312u:
            return "SEC_I_CONTINUE_NEEDED";
          case 0x90313u:
            return "SEC_I_COMPLETE_NEEDED";
          case 0x90314u:
            return "SEC_I_COMPLETE_AND_CONTINUE";
          case 0x90315u:
            return "SEC_I_LOCAL_LOGON";
          case 0x80090300:
            return "SEC_E_INSUFFICIENT_MEMORY";
        }
        v161 = "SEC_E_INVALID_HANDLE";
        v162 = a1 == -2146893055;
      }
    }
    else
    {
      if ( a1 == 11002 )
        return "WSATRY_AGAIN";
      if ( a1 <= 0x2741 )
      {
        if ( a1 == 10049 )
          return "WSAEADDRNOTAVAIL";
        if ( a1 > 0x2733 )
        {
          if ( a1 > 0x273A )
          {
            v138 = a1 - 10043;
            if ( !v138 )
              return "WSAEPROTONOSUPPORT";
            v139 = v138 - 1;
            if ( !v139 )
              return "WSAESOCKTNOSUPPORT";
            v140 = v139 - 1;
            if ( !v140 )
              return "WSAEOPNOTSUPP";
            v141 = v140 - 1;
            if ( !v141 )
              return "WSAEPFNOSUPPORT";
            v142 = v141 - 1;
            if ( !v142 )
              return "WSAEAFNOSUPPORT";
            if ( v142 == 1 )
              return "WSAEADDRINUSE";
          }
          else
          {
            if ( a1 == 10042 )
              return "WSAENOPROTOOPT";
            v133 = a1 - 10036;
            if ( !v133 )
              return "WSAEINPROGRESS";
            v134 = v133 - 1;
            if ( !v134 )
              return "WSAEALREADY";
            v135 = v134 - 1;
            if ( !v135 )
              return "WSAENOTSOCK";
            v136 = v135 - 1;
            if ( !v136 )
              return "WSAEDESTADDRREQ";
            v137 = v136 - 1;
            if ( !v137 )
              return "WSAEMSGSIZE";
            if ( v137 == 1 )
              return "WSAEPROTOTYPE";
          }
        }
        else
        {
          if ( a1 == 10035 )
            return "WSAEWOULDBLOCK";
          if ( a1 > 0x89A )
          {
            v128 = a1 - 10004;
            if ( !v128 )
              return "WSAEINTR";
            v129 = v128 - 5;
            if ( !v129 )
              return "WSAEBADF";
            v130 = v129 - 4;
            if ( !v130 )
              return "WSAEACCES";
            v131 = v130 - 1;
            if ( !v131 )
              return "WSAEFAULT";
            v132 = v131 - 8;
            if ( !v132 )
              return "WSAEINVAL";
            if ( v132 == 2 )
              return "WSAEMFILE";
          }
          else
          {
            if ( a1 == 2202 )
              return "ERROR_BAD_USERNAME";
            v123 = a1 - 1778;
            if ( !v123 )
              return "RPC_X_SS_HANDLES_MISMATCH";
            v124 = v123 - 1;
            if ( !v124 )
              return "RPC_X_SS_CANNOT_GET_CALL_HANDLE";
            v125 = v124 - 1;
            if ( !v125 )
              return "RPC_X_NULL_REF_POINTER";
            v126 = v125 - 1;
            if ( !v126 )
              return "RPC_X_ENUM_VALUE_OUT_OF_RANGE";
            v127 = v126 - 1;
            if ( !v127 )
              return "RPC_X_BYTE_COUNT_TOO_SMALL";
            if ( v127 == 1 )
              return "RPC_X_BAD_STUB_DATA";
          }
        }
        return "?";
      }
      if ( a1 <= 0x2775 )
      {
        if ( a1 == 10101 )
          return "WSAEDISCON";
        if ( a1 > 0x274E )
        {
          if ( a1 > 0x2755 )
          {
            v157 = a1 - 10070;
            if ( !v157 )
              return "WSAESTALE";
            v158 = v157 - 1;
            if ( !v158 )
              return "WSAEREMOTE";
            v159 = v158 - 20;
            if ( !v159 )
              return "WSASYSNOTREADY";
            v160 = v159 - 1;
            if ( !v160 )
              return "WSAVERNOTSUPPORTED";
            if ( v160 == 1 )
              return "WSANOTINITIALISED";
          }
          else
          {
            if ( a1 == 10069 )
              return "WSAEDQUOT";
            v152 = a1 - 10063;
            if ( !v152 )
              return "WSAENAMETOOLONG";
            v153 = v152 - 1;
            if ( !v153 )
              return "WSAEHOSTDOWN";
            v154 = v153 - 1;
            if ( !v154 )
              return "WSAEHOSTUNREACH";
            v155 = v154 - 1;
            if ( !v155 )
              return "WSAENOTEMPTY";
            v156 = v155 - 1;
            if ( !v156 )
              return "WSAEPROCLIM";
            if ( v156 == 1 )
              return "WSAEUSERS";
          }
        }
        else
        {
          if ( a1 == 10062 )
            return "WSAELOOP";
          if ( a1 > 0x2748 )
          {
            v148 = a1 - 10057;
            if ( !v148 )
              return "WSAENOTCONN";
            v149 = v148 - 1;
            if ( !v149 )
              return "WSAESHUTDOWN";
            v150 = v149 - 1;
            if ( !v150 )
              return "WSAETOOMANYREFS";
            v151 = v150 - 1;
            if ( !v151 )
              return "WSAETIMEDOUT";
            if ( v151 == 1 )
              return "WSAECONNREFUSED";
          }
          else
          {
            if ( a1 == 10056 )
              return "WSAEISCONN";
            v143 = a1 - 10050;
            if ( !v143 )
              return "WSAENETDOWN";
            v144 = v143 - 1;
            if ( !v144 )
              return "WSAENETUNREACH";
            v145 = v144 - 1;
            if ( !v145 )
              return "WSAENETRESET";
            v146 = v145 - 1;
            if ( !v146 )
              return "WSAECONNABORTED";
            v147 = v146 - 1;
            if ( !v147 )
              return "WSAECONNRESET";
            if ( v147 == 1 )
              return "WSAENOBUFS";
          }
        }
        return "?";
      }
      v161 = "WSAHOST_NOT_FOUND";
      v162 = a1 == 11001;
    }
    v183 = "?";
    if ( v162 )
      return (char *)v161;
    return (char *)v183;
  }
  if ( a1 == 1777 )
    return "RPC_X_SS_CONTEXT_DAMAGED";
  if ( a1 <= 0x6B5 )
  {
    if ( a1 == 1717 )
      return "RPC_S_UNKNOWN_IF";
    if ( a1 > 0x3F5 )
    {
      if ( a1 > 0x6A7 )
      {
        if ( a1 > 0x6AE )
        {
          v118 = a1 - 1711;
          if ( !v118 )
            return "RPC_S_ALREADY_REGISTERED";
          v119 = v118 - 1;
          if ( !v119 )
            return "RPC_S_TYPE_ALREADY_REGISTERED";
          v120 = v119 - 1;
          if ( !v120 )
            return "RPC_S_ALREADY_LISTENING";
          v121 = v120 - 1;
          if ( !v121 )
            return "RPC_S_NO_PROTSEQS_REGISTERED";
          v122 = v121 - 1;
          if ( !v122 )
            return "RPC_S_NOT_LISTENING";
          if ( v122 == 1 )
            return "RPC_S_UNKNOWN_MGR_TYPE";
        }
        else
        {
          if ( a1 == 1710 )
            return "RPC_S_OBJECT_NOT_FOUND";
          v113 = a1 - 1704;
          if ( !v113 )
            return "RPC_S_INVALID_RPC_PROTSEQ";
          v114 = v113 - 1;
          if ( !v114 )
            return "RPC_S_INVALID_STRING_UUID";
          v115 = v114 - 1;
          if ( !v115 )
            return "RPC_S_INVALID_ENDPOINT_FORMAT";
          v116 = v115 - 1;
          if ( !v116 )
            return "RPC_S_INVALID_NET_ADDR";
          v117 = v116 - 1;
          if ( !v117 )
            return "RPC_S_NO_ENDPOINT_FOUND";
          if ( v117 == 1 )
            return "RPC_S_INVALID_TIMEOUT";
        }
      }
      else
      {
        if ( a1 == 1703 )
          return "RPC_S_PROTSEQ_NOT_SUPPORTED";
        if ( a1 > 0x426 )
        {
          v108 = a1 - 1114;
          if ( !v108 )
            return "ERROR_DLL_INIT_FAILED";
          v109 = v108 - 109;
          if ( !v109 )
            return "ERROR_CANCELLED";
          v110 = v109 - 103;
          if ( !v110 )
            return "ERROR_LOGON_FAILURE";
          v111 = v110 - 374;
          if ( !v111 )
            return "RPC_S_INVALID_STRING_BINDING";
          v112 = v111 - 1;
          if ( !v112 )
            return "RPC_S_WRONG_KIND_OF_BINDING";
          if ( v112 == 1 )
            return "RPC_S_INVALID_BINDING";
        }
        else
        {
          if ( a1 == 1062 )
            return "ERROR_SERVICE_NOT_ACTIVE";
          v103 = a1 - 1014;
          if ( !v103 )
            return "ERROR_REGISTRY_RECOVERED";
          v104 = v103 - 1;
          if ( !v104 )
            return "ERROR_REGISTRY_CORRUPT";
          v105 = v104 - 1;
          if ( !v105 )
            return "ERROR_REGISTRY_IO_FAILED";
          v106 = v105 - 1;
          if ( !v106 )
            return "ERROR_NOT_REGISTRY_FILE";
          v107 = v106 - 1;
          if ( !v107 )
            return "ERROR_KEY_DELETED";
          if ( v107 == 41 )
            return "ERROR_CIRCULAR_DEPENDENCY";
        }
      }
    }
    else
    {
      if ( a1 == 1013 )
        return "ERROR_CANTWRITE";
      if ( a1 > 0x1E7 )
      {
        if ( a1 > 0x3E9 )
        {
          v98 = a1 - 1004;
          if ( !v98 )
            return "ERROR_INVALID_FLAGS";
          v99 = v98 - 4;
          if ( !v99 )
            return "ERROR_NO_TOKEN";
          v100 = v99 - 1;
          if ( !v100 )
            return "ERROR_BADDB";
          v101 = v100 - 1;
          if ( !v101 )
            return "ERROR_BADKEY";
          v102 = v101 - 1;
          if ( !v102 )
            return "ERROR_CANTOPEN";
          if ( v102 == 1 )
            return "ERROR_CANTREAD";
        }
        else
        {
          if ( a1 == 1001 )
            return "ERROR_STACK_OVERFLOW";
          v93 = a1 - 535;
          if ( !v93 )
            return "ERROR_PIPE_CONNECTED";
          v94 = v93 - 1;
          if ( !v94 )
            return "ERROR_PIPE_LISTENING";
          v95 = v94 - 459;
          if ( !v95 )
            return "ERROR_OPERATION_ABORTED";
          v96 = v95 - 1;
          if ( !v96 )
            return "ERROR_IO_INCOMPLETE";
          v97 = v96 - 1;
          if ( !v97 )
            return "ERROR_IO_PENDING";
          if ( v97 == 1 )
            return "ERROR_NOACCESS";
        }
      }
      else
      {
        if ( a1 == 487 )
          return "ERROR_INVALID_ADDRESS";
        if ( a1 > 0xE9 )
        {
          v88 = a1 - 234;
          if ( !v88 )
            return "ERROR_MORE_DATA";
          v89 = v88 - 24;
          if ( !v89 )
            return "WAIT_TIMEOUT";
          v90 = v89 - 1;
          if ( !v90 )
            return "ERROR_NO_MORE_ITEMS";
          v91 = v90 - 29;
          if ( !v91 )
            return "ERROR_NOT_OWNER";
          v92 = v91 - 11;
          if ( !v92 )
            return "ERROR_PARTIAL_COPY";
          if ( v92 == 18 )
            return "ERROR_MR_MID_NOT_FOUND";
        }
        else
        {
          if ( a1 == 233 )
            return "ERROR_PIPE_NOT_CONNECTED";
          v83 = a1 - 206;
          if ( !v83 )
            return "ERROR_FILENAME_EXCED_RANGE";
          v84 = v83 - 6;
          if ( !v84 )
            return "ERROR_LOCKED";
          v85 = v84 - 3;
          if ( !v85 )
            return "ERROR_NESTING_NOT_ALLOWED";
          v86 = v85 - 15;
          if ( !v86 )
            return "ERROR_BAD_PIPE";
          v87 = v86 - 1;
          if ( !v87 )
            return "ERROR_PIPE_BUSY";
          if ( v87 == 1 )
            return "ERROR_NO_DATA";
        }
      }
    }
    return "?";
  }
  switch ( a1 )
  {
    case 0x6B6u:
      result = "RPC_S_NO_BINDINGS";
      break;
    case 0x6B7u:
      result = "RPC_S_NO_PROTSEQS";
      break;
    case 0x6B8u:
      result = "RPC_S_CANT_CREATE_ENDPOINT";
      break;
    case 0x6B9u:
      result = "RPC_S_OUT_OF_RESOURCES";
      break;
    case 0x6BAu:
      result = "RPC_S_SERVER_UNAVAILABLE";
      break;
    case 0x6BBu:
      result = "RPC_S_SERVER_TOO_BUSY";
      break;
    case 0x6BCu:
      result = "RPC_S_INVALID_NETWORK_OPTIONS";
      break;
    case 0x6BDu:
      result = "RPC_S_NO_CALL_ACTIVE";
      break;
    case 0x6BEu:
      result = "RPC_S_CALL_FAILED";
      break;
    case 0x6BFu:
      result = "RPC_S_CALL_FAILED_DNE";
      break;
    case 0x6C0u:
      result = "RPC_S_PROTOCOL_ERROR";
      break;
    case 0x6C2u:
      result = "RPC_S_UNSUPPORTED_TRANS_SYN";
      break;
    case 0x6C4u:
      result = "RPC_S_UNSUPPORTED_TYPE";
      break;
    case 0x6C5u:
      result = "RPC_S_INVALID_TAG";
      break;
    case 0x6C6u:
      result = "RPC_S_INVALID_BOUND";
      break;
    case 0x6C7u:
      result = "RPC_S_NO_ENTRY_NAME";
      break;
    case 0x6C8u:
      result = "RPC_S_INVALID_NAME_SYNTAX";
      break;
    case 0x6C9u:
      result = "RPC_S_UNSUPPORTED_NAME_SYNTAX";
      break;
    case 0x6CBu:
      result = "RPC_S_UUID_NO_ADDRESS";
      break;
    case 0x6CCu:
      result = "RPC_S_DUPLICATE_ENDPOINT";
      break;
    case 0x6CDu:
      result = "RPC_S_UNKNOWN_AUTHN_TYPE";
      break;
    case 0x6CEu:
      result = "RPC_S_MAX_CALLS_TOO_SMALL";
      break;
    case 0x6CFu:
      result = "RPC_S_STRING_TOO_LONG";
      break;
    case 0x6D0u:
      result = "RPC_S_PROTSEQ_NOT_FOUND";
      break;
    case 0x6D1u:
      result = "RPC_S_PROCNUM_OUT_OF_RANGE";
      break;
    case 0x6D2u:
      result = "RPC_S_BINDING_HAS_NO_AUTH";
      break;
    case 0x6D3u:
      result = "RPC_S_UNKNOWN_AUTHN_SERVICE";
      break;
    case 0x6D4u:
      result = "RPC_S_UNKNOWN_AUTHN_LEVEL";
      break;
    case 0x6D5u:
      result = "RPC_S_INVALID_AUTH_IDENTITY";
      break;
    case 0x6D6u:
      result = "RPC_S_UNKNOWN_AUTHZ_SERVICE";
      break;
    case 0x6D7u:
      result = "EPT_S_INVALID_ENTRY";
      break;
    case 0x6D8u:
      result = "EPT_S_CANT_PERFORM_OP";
      break;
    case 0x6D9u:
      result = "EPT_S_NOT_REGISTERED";
      break;
    case 0x6DAu:
      result = "RPC_S_NOTHING_TO_EXPORT";
      break;
    case 0x6DBu:
      result = "RPC_S_INCOMPLETE_NAME";
      break;
    case 0x6DCu:
      result = "RPC_S_INVALID_VERS_OPTION";
      break;
    case 0x6DDu:
      result = "RPC_S_NO_MORE_MEMBERS";
      break;
    case 0x6DEu:
      result = "RPC_S_NOT_ALL_OBJS_UNEXPORTED";
      break;
    case 0x6DFu:
      result = "RPC_S_INTERFACE_NOT_FOUND";
      break;
    case 0x6E0u:
      result = "RPC_S_ENTRY_ALREADY_EXISTS";
      break;
    case 0x6E1u:
      result = "RPC_S_ENTRY_NOT_FOUND";
      break;
    case 0x6E2u:
      result = "RPC_S_NAME_SERVICE_UNAVAILABLE";
      break;
    case 0x6E3u:
      result = "RPC_S_INVALID_NAF_ID";
      break;
    case 0x6E4u:
      result = "RPC_S_CANNOT_SUPPORT";
      break;
    case 0x6E5u:
      result = "RPC_S_NO_CONTEXT_AVAILABLE";
      break;
    case 0x6E6u:
      result = "RPC_S_INTERNAL_ERROR";
      break;
    case 0x6E7u:
      result = "RPC_S_ZERO_DIVIDE";
      break;
    case 0x6E8u:
      result = "RPC_S_ADDRESS_ERROR";
      break;
    case 0x6E9u:
      result = "RPC_S_FP_DIV_ZERO";
      break;
    case 0x6EAu:
      result = "RPC_S_FP_UNDERFLOW";
      break;
    case 0x6EBu:
      result = "RPC_S_FP_OVERFLOW";
      break;
    case 0x6ECu:
      result = "RPC_X_NO_MORE_ENTRIES";
      break;
    case 0x6EDu:
      result = "RPC_X_SS_CHAR_TRANS_OPEN_FAIL";
      break;
    case 0x6EEu:
      result = "RPC_X_SS_CHAR_TRANS_SHORT_FILE";
      break;
    case 0x6EFu:
      result = "RPC_X_SS_IN_NULL_CONTEXT";
      break;
    default:
      return "?";
  }
  return result;
}

```

## disassembly

```asm
0x18008da14  mov     eax, 0C0h
0x18008da19  cmp     ecx, eax
0x18008da1b  ja      loc_18008E08F
0x18008da21  jz      loc_18008E087
0x18008da27  cmp     ecx, 44h ; 'D'
0x18008da2a  ja      loc_18008DD5B
0x18008da30  jz      loc_18008DD53
0x18008da36  cmp     ecx, 1Ch
0x18008da39  ja      loc_18008DBD6
0x18008da3f  jz      loc_18008DBCE
0x18008da45  cmp     ecx, 0Eh
0x18008da48  ja      loc_18008DB1B
0x18008da4e  jz      loc_18008DB13
0x18008da54  cmp     ecx, 7
0x18008da57  ja      short loc_18008DAC1
0x18008da59  jz      short loc_18008DAB9
0x18008da5b  test    ecx, ecx
0x18008da5d  jz      short loc_18008DAB1
0x18008da5f  sub     ecx, 1
0x18008da62  jz      short loc_18008DAA9
0x18008da64  sub     ecx, 1
0x18008da67  jz      short loc_18008DAA1
0x18008da69  sub     ecx, 1
0x18008da6c  jz      short loc_18008DA99
0x18008da6e  sub     ecx, 1
0x18008da71  jz      short loc_18008DA91
0x18008da73  sub     ecx, 1
0x18008da76  jz      short loc_18008DA89
0x18008da78  cmp     ecx, 1
0x18008da7b  jnz     def_18008E428; jumptable 000000018008E428 default case, cases 1729,1731,1738
0x18008da81  lea     rax, aErrorInvalidHa; "ERROR_INVALID_HANDLE"
0x18008da88  retn
0x18008da89  lea     rax, aErrorAccessDen; "ERROR_ACCESS_DENIED"
0x18008da90  retn
0x18008da91  lea     rax, aErrorTooManyOp; "ERROR_TOO_MANY_OPEN_FILES"
0x18008da98  retn
0x18008da99  lea     rax, aErrorPathNotFo; "ERROR_PATH_NOT_FOUND"
0x18008daa0  retn
0x18008daa1  lea     rax, aErrorFileNotFo; "ERROR_FILE_NOT_FOUND"
0x18008daa8  retn
0x18008daa9  lea     rax, aErrorInvalidFu; "ERROR_INVALID_FUNCTION"
0x18008dab0  retn
0x18008dab1  lea     rax, aErrorSuccess; "ERROR_SUCCESS"
0x18008dab8  retn
0x18008dab9  lea     rax, aErrorArenaTras; "ERROR_ARENA_TRASHED"
0x18008dac0  retn
0x18008dac1  sub     ecx, 8
0x18008dac4  jz      short loc_18008DB0B
0x18008dac6  sub     ecx, 1
0x18008dac9  jz      short loc_18008DB03
0x18008dacb  sub     ecx, 1
0x18008dace  jz      short loc_18008DAFB
0x18008dad0  sub     ecx, 1
0x18008dad3  jz      short loc_18008DAF3
0x18008dad5  sub     ecx, 1
0x18008dad8  jz      short loc_18008DAEB
0x18008dada  cmp     ecx, 1
0x18008dadd  jnz     def_18008E428; jumptable 000000018008E428 default case, cases 1729,1731,1738
0x18008dae3  lea     rax, aErrorInvalidDa; "ERROR_INVALID_DATA"
0x18008daea  retn
0x18008daeb  lea     rax, aErrorInvalidAc; "ERROR_INVALID_ACCESS"
0x18008daf2  retn
0x18008daf3  lea     rax, aErrorBadFormat; "ERROR_BAD_FORMAT"
0x18008dafa  retn
0x18008dafb  lea     rax, aErrorBadEnviro; "ERROR_BAD_ENVIRONMENT"
0x18008db02  retn
0x18008db03  lea     rax, aErrorInvalidBl; "ERROR_INVALID_BLOCK"
0x18008db0a  retn
0x18008db0b  lea     rax, aErrorNotEnough; "ERROR_NOT_ENOUGH_MEMORY"
0x18008db12  retn
0x18008db13  lea     rax, aErrorOutofmemo; "ERROR_OUTOFMEMORY"
0x18008db1a  retn
0x18008db1b  cmp     ecx, 15h
0x18008db1e  ja      short loc_18008DB7C
0x18008db20  jz      short loc_18008DB74
0x18008db22  sub     ecx, 0Fh
0x18008db25  jz      short loc_18008DB6C
0x18008db27  sub     ecx, 1
0x18008db2a  jz      short loc_18008DB64
0x18008db2c  sub     ecx, 1
0x18008db2f  jz      short loc_18008DB5C
0x18008db31  sub     ecx, 1
0x18008db34  jz      short loc_18008DB54
0x18008db36  sub     ecx, 1
0x18008db39  jz      short loc_18008DB4C
0x18008db3b  cmp     ecx, 1
0x18008db3e  jnz     def_18008E428; jumptable 000000018008E428 default case, cases 1729,1731,1738
0x18008db44  lea     rax, aErrorBadUnit; "ERROR_BAD_UNIT"
0x18008db4b  retn
0x18008db4c  lea     rax, aErrorWriteProt; "ERROR_WRITE_PROTECT"
0x18008db53  retn
0x18008db54  lea     rax, aErrorNoMoreFil; "ERROR_NO_MORE_FILES"
0x18008db5b  retn
0x18008db5c  lea     rax, aErrorNotSameDe; "ERROR_NOT_SAME_DEVICE"
0x18008db63  retn
0x18008db64  lea     rax, aErrorCurrentDi; "ERROR_CURRENT_DIRECTORY"
0x18008db6b  retn
0x18008db6c  lea     rax, aErrorInvalidDr; "ERROR_INVALID_DRIVE"
0x18008db73  retn
0x18008db74  lea     rax, aErrorNotReady; "ERROR_NOT_READY"
0x18008db7b  retn
0x18008db7c  sub     ecx, 16h
0x18008db7f  jz      short loc_18008DBC6
0x18008db81  sub     ecx, 1
0x18008db84  jz      short loc_18008DBBE
0x18008db86  sub     ecx, 1
0x18008db89  jz      short loc_18008DBB6
0x18008db8b  sub     ecx, 1
0x18008db8e  jz      short loc_18008DBAE
0x18008db90  sub     ecx, 1
0x18008db93  jz      short loc_18008DBA6
0x18008db95  cmp     ecx, 1
0x18008db98  jnz     def_18008E428; jumptable 000000018008E428 default case, cases 1729,1731,1738
0x18008db9e  lea     rax, aErrorSectorNot; "ERROR_SECTOR_NOT_FOUND"
0x18008dba5  retn
0x18008dba6  lea     rax, aErrorNotDosDis; "ERROR_NOT_DOS_DISK"
0x18008dbad  retn
0x18008dbae  lea     rax, aErrorSeek; "ERROR_SEEK"
0x18008dbb5  retn
0x18008dbb6  lea     rax, aErrorBadLength; "ERROR_BAD_LENGTH"
0x18008dbbd  retn
0x18008dbbe  lea     rax, aErrorCrc; "ERROR_CRC"
0x18008dbc5  retn
0x18008dbc6  lea     rax, aErrorBadComman; "ERROR_BAD_COMMAND"
0x18008dbcd  retn
0x18008dbce  lea     rax, aErrorOutOfPape; "ERROR_OUT_OF_PAPER"
0x18008dbd5  retn
0x18008dbd6  cmp     ecx, 36h ; '6'
0x18008dbd9  ja      loc_18008DCA0
0x18008dbdf  jz      loc_18008DC98
0x18008dbe5  cmp     ecx, 24h ; '$'
0x18008dbe8  ja      short loc_18008DC46
0x18008dbea  jz      short loc_18008DC3E
0x18008dbec  sub     ecx, 1Dh
0x18008dbef  jz      short loc_18008DC36
0x18008dbf1  sub     ecx, 1
0x18008dbf4  jz      short loc_18008DC2E
0x18008dbf6  sub     ecx, 1
0x18008dbf9  jz      short loc_18008DC26
0x18008dbfb  sub     ecx, 1
0x18008dbfe  jz      short loc_18008DC1E
0x18008dc00  sub     ecx, 1
0x18008dc03  jz      short loc_18008DC16
0x18008dc05  cmp     ecx, 1
0x18008dc08  jnz     def_18008E428; jumptable 000000018008E428 default case, cases 1729,1731,1738
0x18008dc0e  lea     rax, aErrorWrongDisk; "ERROR_WRONG_DISK"
0x18008dc15  retn
0x18008dc16  lea     rax, aErrorLockViola; "ERROR_LOCK_VIOLATION"
0x18008dc1d  retn
0x18008dc1e  lea     rax, aErrorSharingVi; "ERROR_SHARING_VIOLATION"
0x18008dc25  retn
0x18008dc26  lea     rax, aErrorGenFailur; "ERROR_GEN_FAILURE"
0x18008dc2d  retn
0x18008dc2e  lea     rax, aErrorReadFault; "ERROR_READ_FAULT"
0x18008dc35  retn
0x18008dc36  lea     rax, aErrorWriteFaul; "ERROR_WRITE_FAULT"
0x18008dc3d  retn
0x18008dc3e  lea     rax, aErrorSharingBu; "ERROR_SHARING_BUFFER_EXCEEDED"
0x18008dc45  retn
0x18008dc46  sub     ecx, 26h ; '&'
0x18008dc49  jz      short loc_18008DC90
0x18008dc4b  sub     ecx, 1
0x18008dc4e  jz      short loc_18008DC88
0x18008dc50  sub     ecx, 0Bh
0x18008dc53  jz      short loc_18008DC80
0x18008dc55  sub     ecx, 1
0x18008dc58  jz      short loc_18008DC78
0x18008dc5a  sub     ecx, 1
0x18008dc5d  jz      short loc_18008DC70
0x18008dc5f  cmp     ecx, 1
0x18008dc62  jnz     def_18008E428; jumptable 000000018008E428 default case, cases 1729,1731,1738
0x18008dc68  lea     rax, aErrorBadNetpat; "ERROR_BAD_NETPATH"
0x18008dc6f  retn
0x18008dc70  lea     rax, aErrorDupName; "ERROR_DUP_NAME"
0x18008dc77  retn
0x18008dc78  lea     rax, aErrorRemNotLis; "ERROR_REM_NOT_LIST"
0x18008dc7f  retn
0x18008dc80  lea     rax, aErrorNotSuppor; "ERROR_NOT_SUPPORTED"
0x18008dc87  retn
0x18008dc88  lea     rax, aErrorHandleDis; "ERROR_HANDLE_DISK_FULL"
0x18008dc8f  retn
0x18008dc90  lea     rax, aErrorHandleEof; "ERROR_HANDLE_EOF"
0x18008dc97  retn
0x18008dc98  lea     rax, aErrorNetworkBu; "ERROR_NETWORK_BUSY"
0x18008dc9f  retn
0x18008dca0  cmp     ecx, 3Dh ; '='
0x18008dca3  ja      short loc_18008DD01
0x18008dca5  jz      short loc_18008DCF9
0x18008dca7  sub     ecx, 37h ; '7'
0x18008dcaa  jz      short loc_18008DCF1
0x18008dcac  sub     ecx, 1
0x18008dcaf  jz      short loc_18008DCE9
0x18008dcb1  sub     ecx, 1
0x18008dcb4  jz      short loc_18008DCE1
0x18008dcb6  sub     ecx, 1
0x18008dcb9  jz      short loc_18008DCD9
0x18008dcbb  sub     ecx, 1
0x18008dcbe  jz      short loc_18008DCD1
0x18008dcc0  cmp     ecx, 1
0x18008dcc3  jnz     def_18008E428; jumptable 000000018008E428 default case, cases 1729,1731,1738
0x18008dcc9  lea     rax, aErrorBadRemAda; "ERROR_BAD_REM_ADAP"
0x18008dcd0  retn
0x18008dcd1  lea     rax, aErrorUnexpNetE; "ERROR_UNEXP_NET_ERR"
0x18008dcd8  retn
0x18008dcd9  lea     rax, aErrorBadNetRes; "ERROR_BAD_NET_RESP"
0x18008dce0  retn
0x18008dce1  lea     rax, aErrorAdapHdwEr; "ERROR_ADAP_HDW_ERR"
0x18008dce8  retn
0x18008dce9  lea     rax, aErrorTooManyCm; "ERROR_TOO_MANY_CMDS"
0x18008dcf0  retn
0x18008dcf1  lea     rax, aErrorDevNotExi; "ERROR_DEV_NOT_EXIST"
0x18008dcf8  retn
0x18008dcf9  lea     rax, aErrorPrintqFul; "ERROR_PRINTQ_FULL"
0x18008dd00  retn
0x18008dd01  sub     ecx, 3Eh ; '>'
0x18008dd04  jz      short loc_18008DD4B
0x18008dd06  sub     ecx, 1
0x18008dd09  jz      short loc_18008DD43
0x18008dd0b  sub     ecx, 1
0x18008dd0e  jz      short loc_18008DD3B
0x18008dd10  sub     ecx, 1
0x18008dd13  jz      short loc_18008DD33
0x18008dd15  sub     ecx, 1
0x18008dd18  jz      short loc_18008DD2B
0x18008dd1a  cmp     ecx, 1
0x18008dd1d  jnz     def_18008E428; jumptable 000000018008E428 default case, cases 1729,1731,1738
0x18008dd23  lea     rax, aErrorBadNetNam; "ERROR_BAD_NET_NAME"
0x18008dd2a  retn
0x18008dd2b  lea     rax, aErrorBadDevTyp; "ERROR_BAD_DEV_TYPE"
0x18008dd32  retn
0x18008dd33  lea     rax, aErrorNetworkAc; "ERROR_NETWORK_ACCESS_DENIED"
0x18008dd3a  retn
0x18008dd3b  lea     rax, aErrorNetnameDe; "ERROR_NETNAME_DELETED"
0x18008dd42  retn
0x18008dd43  lea     rax, aErrorPrintCanc; "ERROR_PRINT_CANCELLED"
0x18008dd4a  retn
0x18008dd4b  lea     rax, aErrorNoSpoolSp; "ERROR_NO_SPOOL_SPACE"
0x18008dd52  retn
0x18008dd53  lea     rax, aErrorTooManyNa; "ERROR_TOO_MANY_NAMES"
0x18008dd5a  retn
0x18008dd5b  cmp     ecx, 75h ; 'u'
0x18008dd5e  ja      loc_18008DEFC
0x18008dd64  jz      loc_18008DEF4
0x18008dd6a  cmp     ecx, 65h ; 'e'
0x18008dd6d  ja      loc_18008DE41
0x18008dd73  jz      loc_18008DE39
0x18008dd79  cmp     ecx, 54h ; 'T'
0x18008dd7c  ja      short loc_18008DDE7
0x18008dd7e  jz      short loc_18008DDDF
0x18008dd80  sub     ecx, 45h ; 'E'
0x18008dd83  jz      short loc_18008DDD7
0x18008dd85  sub     ecx, 1
0x18008dd88  jz      short loc_18008DDCF
0x18008dd8a  sub     ecx, 1
0x18008dd8d  jz      short loc_18008DDC7
0x18008dd8f  sub     ecx, 1
0x18008dd92  jz      short loc_18008DDBF
0x18008dd94  sub     ecx, 8
0x18008dd97  jz      short loc_18008DDB7
0x18008dd99  sub     ecx, 2
0x18008dd9c  jz      short loc_18008DDAF
0x18008dd9e  cmp     ecx, 1
0x18008dda1  jnz     def_18008E428; jumptable 000000018008E428 default case, cases 1729,1731,1738
0x18008dda7  lea     rax, aErrorFailI24; "ERROR_FAIL_I24"
0x18008ddae  retn
0x18008ddaf  lea     rax, aErrorCannotMak; "ERROR_CANNOT_MAKE"
0x18008ddb6  retn
0x18008ddb7  lea     rax, aErrorFileExist; "ERROR_FILE_EXISTS"
0x18008ddbe  retn
0x18008ddbf  lea     rax, aErrorRedirPaus; "ERROR_REDIR_PAUSED"
0x18008ddc6  retn
0x18008ddc7  lea     rax, aErrorReqNotAcc; "ERROR_REQ_NOT_ACCEP"
0x18008ddce  retn
0x18008ddcf  lea     rax, aErrorSharingPa; "ERROR_SHARING_PAUSED"
0x18008ddd6  retn
0x18008ddd7  lea     rax, aErrorTooManySe_0; "ERROR_TOO_MANY_SESS"
0x18008ddde  retn
0x18008dddf  lea     rax, aErrorOutOfStru; "ERROR_OUT_OF_STRUCTURES"
0x18008dde6  retn
0x18008dde7  sub     ecx, 55h ; 'U'
0x18008ddea  jz      short loc_18008DE31
0x18008ddec  sub     ecx, 1
0x18008ddef  jz      short loc_18008DE29
0x18008ddf1  sub     ecx, 1
0x18008ddf4  jz      short loc_18008DE21
0x18008ddf6  sub     ecx, 1
0x18008ddf9  jz      short loc_18008DE19
0x18008ddfb  sub     ecx, 1
0x18008ddfe  jz      short loc_18008DE11
0x18008de00  cmp     ecx, 0Bh
0x18008de03  jnz     def_18008E428; jumptable 000000018008E428 default case, cases 1729,1731,1738
0x18008de09  lea     rax, aErrorTooManySe; "ERROR_TOO_MANY_SEMAPHORES"
0x18008de10  retn
0x18008de11  lea     rax, aErrorNoProcSlo; "ERROR_NO_PROC_SLOTS"
0x18008de18  retn
0x18008de19  lea     rax, aErrorNetWriteF; "ERROR_NET_WRITE_FAULT"
0x18008de20  retn
0x18008de21  lea     rax, aErrorInvalidPa; "ERROR_INVALID_PARAMETER"
0x18008de28  retn
0x18008de29  lea     rax, aErrorInvalidPa_0; "ERROR_INVALID_PASSWORD"
  ... truncated ...
```
